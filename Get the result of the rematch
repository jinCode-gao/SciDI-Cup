import numpy as np
import os
import csv

import outlier
import matplotlib.pyplot as plt

result=[]
left=[]
right=[]
nm=1
cishu=1
# 打开文件
path = "F:/夜观天象/复赛数据2/AstroSet"
dirs2 = os.listdir(path)

for f in dirs2:
    path2=path+'/'+f
    dirs=os.listdir(path2)

    #min_outlier_rate=0.004
    i=1
    j=1
    for file_name in dirs:#取一个文件名
        if file_name=="abstract":
            continue
        print("cishu",cishu)
        cishu+=1
        P=path2+"/"+file_name

        #print("路径", P)

        t1 = np.loadtxt(P, delimiter=",", dtype="float64")

        y = t1[:, 1]

        num = len(y)
        x = []
        i = 1
        while True:
            x.append(i)
            i += 1
            if i > num:
                break

        # 异常点叠加显示
        outlier_all, outlier_rate = outlier.o_t(t1)  # 获取全部异常点
        outlier_section_list = outlier.outlierlist_detect(outlier_all, t1)  # 获取全部异常区间

        for i in outlier_section_list:  # 读取每一个异常区间
            left_outlier_boundary_num, right_outlier_boundary_num, num_min= outlier.detect(i[0], t1)

            left_outlier_boundary=t1[left_outlier_boundary_num,0]
            right_outlier_boundary=t1[right_outlier_boundary_num,0]

            outliers_rate,slope_difference,d=outlier.data_analysis(i, num_min, t1)

            if(outlier.judge(left_outlier_boundary_num, right_outlier_boundary_num, num_min,left_outlier_boundary,right_outlier_boundary,outliers_rate,slope_difference,d,t1,i)):
                result.append(file_name)  # 可能有重复，待修改
                left.append(left_outlier_boundary)
                right.append(right_outlier_boundary)
                print("nm", nm)
                nm += 1

            # if outliers_rate > 0.02:  # 筛选标准1
            #     slope_left = (t1[i[0], 1] - t1[num_min, 1]) / (num_min - i[0])
            #     slope_right = (t1[i[1], 1] - t1[num_min, 1]) / (i[1] - num_min)
            #
            #     if slope_left >= 0.01 and slope_right>0.001:#情况一
            #         if float(slope_left)/float(slope_right)>5:#5倍
            #             if d > 0.38:  # 筛选标准3 官方说是0.478，此前用0.38得0.0168分
            #
            #                 result.append(file_name)  # 可能有重复，待修改
            #                 left.append(left_outlier_boundary)
            #                 right.append(right_outlier_boundary)
            #
            #                 print("nm", nm)
            #                 nm += 1
            #                 print("********************************************************************************************")
            #
            #     else:#情况二
            #         if slope_difference>0.001:#筛选标准2
            #
            #             if d>0.38:   #筛选标准3 官方说是0.478，此前用0.38得0.0168分
            #
            #                 result.append(file_name)  # 可能有重复，待修改
            #                 left.append(left_outlier_boundary)
            #                 right.append(right_outlier_boundary)
            #
            #                 print("nm", nm)
            #                 nm += 1
            #                 print(
            #                     "********************************************************************************************")

with open('d:/Result8_.csv', 'w', newline='') as csvfile:
    writer = csv.writer(csvfile)
    for row in result:
        writer.writerow([row,'flare star'])

with open('d:/Result_left8_.csv', 'w', newline='') as csvfile:
    writer = csv.writer(csvfile)
    for l in left:
        writer.writerow([l])

with open('d:/Result_right8_.csv', 'w', newline='') as csvfile:
    writer = csv.writer(csvfile)
    for r in right:
        writer.writerow([r])
