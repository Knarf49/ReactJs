def romanToInt(x):
    r_map={
        '':0,
        ' ':0,
        'I':1,
        'V':5,
        'X':10,
        'L':50,
        'C':100,
        'D':500,
        'M':1000
    }
    if type(x)!=str:
        return 'Error'
    for i in x:
        if i not in r_map.keys():
            return 'Error'
    res=0
    other_sum=0
    f=x[0:1]
    s=x[1:2]
    other= x[2:]
    other_tuple = tuple(other)
    r_list=[]

    for char in range(0,len(x),2):
        # print(f'char={char}')
        if char+2<=len(x)+1:
            r_list.append(x[char:char+2])
    # print(r_list)

    #change other to num
    # for char in other:
    #     other_sum+=r_map[char]

    # for roman in range(len(x)//2):
    #     if roman <= len(x):
    #         if r_map[f]<r_map[s]:
    #             res = r_map[s]- r_map[f]
    #             print(f'{r_map[f]} - {r_map[s]}')
    #         elif r_map[f] >= r_map[s]: 
    #             res = r_map[f] + r_map[s]
    #             print(f'{r_map[f]} + {r_map[s]}')
        
    # print(f'+ {other_sum}')
    # res+=other_sum
    # print(f'r_list={r_list}')
    for j in range(len(r_list)):
        f=r_list[j][0]  
        if len(r_list[j])%2==0:  
            s=r_list[j][1]
        else:
            s=' '
        # print(f'f={f}')
        # print(f's={s}')
        if r_map[f]<r_map[s]:
                res += r_map[s]- r_map[f]
                # print(f'{r_map[s]} - {r_map[f]}')
        elif r_map[f] >= r_map[s]: 
                res += r_map[f] + r_map[s]
                # print(f'{r_map[f]} + {r_map[s]}')
    #if f<s return true else false
    # print(len(r_list))
    return res

print(romanToInt('DCCCXLVII'))

# print(len(x)//2 +1)

# for roman in range(len(x)):
#     if roman <= len(x):
#         print(x[roman:roman+1])

#change f,s value
# x='cccxxvi'
# l2=['cc','cx','xv','i']
# for i in range(0,len(x),2):
#     print(i)

# print(len(x))
# print(romanToInt('VI'))

# l=['LX','VI','I']
# print(len(l[2]))
