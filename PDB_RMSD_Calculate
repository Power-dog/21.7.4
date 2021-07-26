# 한 파일 내에서의 MODEL n과 n2의 RMSD를 비교하는 프로그램
def pdb(n, n2):
    import math
    p = open("C:/Users/SML/Desktop/우원/7월/3주/1l2y.pdb", 'r').read().split('\nMODEL')   # MODEL 단위로 나눠줌
    p2 = "".join(p[n])                                                           # n번째 MODEL 이후 다음 MODEL 전까지 전체 문자열
    p3 = p2[p2.index('ATOM'):p2.index('TER')-1]                                  # 76:24700-1. xyz좌표 있는 것들만 따로 모아 문자열로
    p4 = p3.split('\n')                                                          # xyz 있는 것들 한 줄씩 나눠 리스트로 (304줄)

    d2 = "".join(p[n2])
    d3 = d2[d2.index('ATOM'):d2.index('TER')-1]
    d4 = d3.split('\n')

    # x,y,z값 따로 모으기
    x1=[]
    y1=[]
    z1=[]
    for i in range(len(p4)):                                                     # x,y,z 각각 모아 리스트 한줄에 저장
        x1.append(float(p4[i].split()[6]))
        y1.append(float(p4[i].split()[7]))
        z1.append(float(p4[i].split()[8]))

    x2=[]
    y2=[]
    z2=[]
    for i in range(len(d4)):
        x2.append(float(d4[i].split()[6]))
        y2.append(float(d4[i].split()[7]))
        z2.append(float(d4[i].split()[8]))

    # RMSD(RMSE) 계산
    r=[]
    for i in range(len(p4)):                                                     # (x2-x1)^2 + (y2-y1)^2... 한 값들을 r에 저장
        r.append((float(x2[i]-x1[i]))**2 + float((y2[i]-y1[i]))**2 + float((z2[i]-z1[i]))**2)
    print(math.sqrt(sum(r)/len(p4)))                                             # r 더한것에서 전체 수를 나눠주고 루트

pdb(1, 4)
