# Information-Security-Project
#Software Security Project( Secure Sharing of Information Using an Algorithm namely KAN) using python and java

import random
class encryption:
    list=[' ','.',',','@','A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z','He','Li','Be','Ne','Na','Mg','Al','Si','Ar','Ca','Sc','Ti','Cr','Mn','Fe','Co','Ni','Cu','Zn','Ga','Ge','As','Se','Br','Kr','Rb','Sr','Zr','Nb','Mo','Tc','Ru','Rh','Pd','Ag','Cd','In','Sn','Sb','Te','Xe','Cs','Ba','Hf','Ta','Re','Os','Ir','Pt','Au','Hg','Pb','Bi','Po','At','Rn','Fr','Ra','Rf','Db','Sg','Bh','Hs','Mt','Ds','Rg','Cn','Nh','Fi','Mc','Lv','Ts','Og','La','Ce','Pr','Nd','Pm','Sm','Eu','Gd','Tb','Dy','Ho','Er','Tm','Yb','Lu','Ac','Th','Pa','Np','Pu','Am','Cm','Bk','Cf','Es','Fm','Md','No','Lr']
    list1=[' ','.',',','@','A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z','He','Li','Be','Ne','Na','Mg','Al','Si','Ar','Ca','Sc','Ti','Cr','Mn','Fe','Co','Ni','Cu','Zn','Ga','Ge','As','Se','Br','Kr','Rb','Sr','Zr','Nb','Mo','Tc','Ru','Rh','Pd','Ag','Cd','In','Sn','Sb','Te','Xe','Cs','Ba','Hf','Ta','Re','Os','Ir','Pt','Au','Hg','Pb','Bi','Po','At','Rn','Fr','Ra','Rf','Db','Sg','Bh','Hs','Mt','Ds','Rg','Cn','Nh','Fi','Mc','Lv','Ts','Og','La','Ce','Pr','Nd','Pm','Sm','Eu','Gd','Tb','Dy','Ho','Er','Tm','Yb','Lu','Ac','Th','Pa','Np','Pu','Am','Cm','Bk','Cf','Es','Fm','Md','No','Lr']
    list2=[]
    list3=[]
    list4=[]
    listprime=[2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97,101, 103, 107, 109, 113, 127, 131, 137, 139, 149, 151, 157, 163, 167, 173, 179, 183, 193, 197, 199,211, 223, 227, 229, 233, 239, 241, 251, 257, 263, 269, 271, 277, 281, 283, 293,307, 311, 313, 317, 331, 337, 347, 349, 353, 359, 367, 373, 379, 383, 389, 397,401, 409, 419, 421, 431, 433, 439, 443, 449, 457, 461, 463, 467, 479, 487, 491, 499,503, 509, 521, 523, 541, 547, 557, 563, 569, 571, 577, 587, 593, 599]
    list5=[3]
    list6=[]
    list8=[]
    list9=[]
    list15=[]
    string= raw_input("Enter the string");
    string=string.upper();
    len_originalstring=len(string)
    space_value= random.choice(list5)
    N=len_originalstring*(space_value+1)
    #print "....................",N
    temp=''
    for j in range(0,len(string)):
        temp1=''
        for i in range(0,space_value):
            list[i]=random.choice(list1[4:])
            temp1=temp1+list[i]
        temp=temp+string[j]+temp1
    print "before encryption without key",temp
    key_value=(space_value-1)*(len_originalstring*(space_value+1))
    print "key_value",key_value
    for i in range(0,len(list1)):
                for j in range(i,len(list1)):
                    if(i*j==key_value):
                        str1=list1[i]
                        str2=list1[j]
                        str3="*"
                        str=str1+str2+str3
                        #print str
                    elif(i+j==key_value):
                        str1=list1[i]
                        str2=list1[j]
                        str3="+"
                        str=str1+str2+str3
                        #print str
    key_concat=temp+str
    print "before encryption with key",key_concat
    if(str3=='*'):
            key_message=list1.index(str1)*list1.index(str2)
            #print key_message
    if(str3=='+'):
            key_message=list1.index(str1)+list1.index(str2)
            #print key_message
    print str
    list10=[]
    count=0
    i=0
    for j in range(0,len(temp)):
        if(temp[j].islower()):
            count=count+1



    for k in range(0,len(temp)-count):
        if(i+1<len(temp)):
            if(temp[i+1].islower()):
                text=temp[i]+temp[i+1]
                i=i+2
                #print text
                for j in range(0,len(list1)):
                    if(text==list1[j]):
                        list10.append(j)
            elif(temp[i+1].isupper()):
                text=temp[i]
                i=i+1
                #print text
                for j in range(0,len(list1)):
                    if(text==list1[j]):
                        list10.append(j)
            elif(temp[i+1]=='@'):
                text=temp[i]
                i=i+1
                #print text
                for j in range(0,len(list1)):
                    if(text==list1[j]):
                        list10.append(j)
            elif(temp[i+1]=='.'):
                text=temp[i]
                i=i+1
                #print text
                for j in range(0,len(list1)):
                    if(text==list1[j]):
                        list10.append(j)
            elif(temp[i+1]==','):
                text=temp[i]
                i=i+1
                #print text
                for j in range(0,len(list1)):
                    if(text==list1[j]):
                        list10.append(j)
            elif(temp[i+1]==' '):
                text=temp[i]
                i=i+1
                #print text
                for j in range(0,len(list1)):
                    if(text==list1[j]):
                        list10.append(j)
        elif(i+1==len(temp)):
            text=temp[i]
            #print text
            for j in range(0,len(list1)):
                    if(text==list1[j]):
                        list10.append(j)
    #print list10
    strtt=''
    for k in range(0,len(list10)):
        encrypted_value=((key_message)*list10[k])/N
        print 'encrypted_value',encrypted_value
        list3.append(encrypted_value);
    for k in range(0,len(list3)):
         if(list3[k]>=len(list1)):
                for i in range(0,len(list1)):
                       for j in range(i,len(list1)):
                               value2=list1.index(list1[i])* list1.index(list1[j])
                               value3=list1.index(list1[i])+ list1.index(list1[j])
                               if(value2==list3[k]):
                                   str1=list1[i]
                                   str2=list1[j]
                                   str3="*"
                                   strtt=str1+str2+str3
                               elif(value3==list3[k]):
                                    str1=list1[i]
                                    str2=list1[j]
                                    str3="+"
                                    strtt=str1+str2+str3
         elif(list3[k]<len(list1)):
             #print list3[k]
             strtt=list1[list3[k]]
         list4.append(strtt)
    #print "list3",list3
    #print "=============",list4
    #print"--------------------------",len(list4)
    #print"**************************",len(list3)
    #print len(list4)
    #print temp
    temp_concat=''
    for i in range(0,len(list4)):
         temp_concat=temp_concat+list4[i]
    #print temp_concat
    string_value=''
    #for i in range(0,len(list1)):
        #for j in range(i,len(list1)):
            #value2=list1.index(list1[i])* list1.index(list1[j])
            #value3=list1.index(list1[i])+ list1.index(list1[j])
            #if(value2==key_message):
                #string1=list1[i]
                #string2=list1[j]
                #string3="*"
                #string_value=string1+string2+string3
                #print string_value
            #if(value3==key_message):
                #string1=list1[i]
                #string2=list1[j]
                #string3="+"
                #string_value=string1+string2+string3
                #print string_value
                #print key_message
    key_with_encryptedstring=temp_concat+str
    #print "temp_concat",temp_concat
    #print "++++++++++++++",key_with_encryptedstring
    key_encryptedvalue=str[len(str)-1:]
    #print "encrypted string",key_with_encryptedstring
    #print "key message",str
    
    list11=[]
    if(key_encryptedvalue=='+'):
        ln=len(str)-1
        #print "length",ln
    elif(key_encryptedvalue=='*'):
        ln=len(str)-1
        #print "length",ln
    else:
        ln=len(str)
        #print "length",ln
    countt=0
    i=0
    for j in range(0,ln):
        if(str[j].islower()):
            countt=countt+1
            #print countt
    for k in range(0,ln-countt):
        if(i+1<ln):
            if(str[i+1].islower()):
                strt=str[i]+str[i+1]
                list11.append(strt)
                i=i+2
            elif(str[i+1].isupper()):
                list11.append(str[i])
                i=i+1
        elif(i+1>len(str)):
            list11.append(str[i])
    list12=[]
    #print len(list11)
    #print list11

    for t in range(0,len(list11)):
        for j in range(0,len(list1)):
            if(list11[t]==list1[j]):
                list12.append(j)
                #print j
    if(key_encryptedvalue=='*'):
        if(len(list12)>1):
            key_encry_value=list12[0]*list12[1]
          #print key_encry_value
    elif(key_encryptedvalue=='+'):
        if(len(list12)>1):
            key_encry_value=list12[0]+list12[1]
          #print key_encry_value
    else:
        key_encry_value=list12[0]
        #print "***********",key_encry_value
    try:
        input = raw_input
    except NameError:
        pass
    p=random.choice(listprime)
    q=random.choice(listprime)
    n=p*q
    #print("n = p * q = " + str(n) + "\n")
    phi=(p-1)*(q-1)
    def gcd(a, b):
        while b != 0:
            c = a % b
            a = b
            b = c
        return a
    def modinv(a, m):
        for x in range(1, m):
            if (a * x) % m == 1:
                return x
        return None
    def coprimes(a):
        l = []
        for x in range(2, a):
            if gcd(a, x) == 1 and modinv(x,phi) != None:
                l.append(x)
        for x in l:
            if x == modinv(x,phi):
                l.remove(x)
        return l
    #print("Choose an e from a below coprimes array:\n")
    #print(coprimes(phi) + "\n")
    e=random.choice(listprime)
    d=modinv(e,phi)
    if(d==None):
        exit
    #print "key_value",key_value
    m = key_value
    rem1 = m**e/n
    rem1 = int(rem1)
    rem2 = rem1*n
    c = m**e - rem2
    #print('Cyphertext:', c)
    rem11 = c**d/n
    rem11 = int(rem11)
    rem22 = rem11*n
    m = c**d - rem22
    #print m


    key_message_value=m
    temp_concat1=''
    string_value1=''
    decrypt_key_value=m
    key_decry_value=key_message
    for i in range(0,len(list1)):
        for j in range(i,len(list1)):
            value4=list1.index(list1[i])* list1.index(list1[j])
            value5=list1.index(list1[i])+ list1.index(list1[j])
            if(value4==decrypt_key_value):
                string1=list1[i]
                string2=list1[j]
                string3="*"
                string_value1=string1+string2+string3
            if(value5==decrypt_key_value):
                string1=list1[i]
                string2=list1[j]
                string3="+"
                string_value1=string1+string2+string3
            #else:
            #    string_value1=list1[i]
    print "*************key value before decrypt the string***************\n",string_value1
    print "**********************Encryptedstring**************************\n",key_with_encryptedstring
    key_with_decryptedstring=''
    list13=[]
    string_value11=key_with_encryptedstring
    i=0



    for k in range(0,len(string_value11)):
        for j in range(0,len(list1)):
            if(i+2<len(string_value11)):
                if(string_value11[i+2]=='+'):
                    text1=string_value11[i]+string_value11[i+1]+string_value11[i+2]
                    list13.append(text1)
                    i=i+3
                    #print i
                elif(string_value11[i+2]=='*'):
                    text1=string_value11[i]+string_value11[i+1]+string_value11[i+2]
                    list13.append(text1)
                    i=i+3
                    #print i
                elif(string_value11[i+1].islower()):
                    text1=string_value11[i]+string_value11[i+1]
                    list13.append(text1)
                    i=i+2
                elif(string_value11[i]==list1[j]):
                    text1=string_value11[i]
                    list13.append(text1)
                    i=i+1
                    #print i
            elif(i+1<len(string_value11)):
                if(string_value11[i+1].islower()):
                    text1=string_value11[i]+string_value11[i+1]
                    list13.append(text1)
                    i=i+2
                elif(string_value11[i]==list1[j]):
                    text1=string_value11[i]
                    list13.append(text1)
                    i=i+1
                    #print i
            elif(i<len(string_value11)):
                if(string_value11[i]==list1[j]):
                    text1=string_value11[i]
                    list13.append(text1)
                    i=i+1
                    #print i
    print "list13",list13
    counttt=0
    for j in range(0,len(string_value1)):
        if(string_value1[j].islower()):
            counttt=counttt+1



    i=0
    if(string_value1[len(string_value1)-1]=='+'):
        string_value11=string_value1[:-1]
        #print string_value11
    
    for k in range(0,len(string_value11)-counttt):
        if(i+1<len(string_value11)):
            if(string_value11[i+1].islower()):
                text=string_value11[i]+string_value11[i+1]
                i=i+2
                #print text
                list15.append(text)
            elif(string_value11[i+1].isupper()):
                text=string_value11[i]
                i=i+1
                #print text
                list15.append(text)
        elif(i+1==len(string_value11)):
            text=string_value11[i]
            #print text
            list15.append(text)
    #print "length of list15",len(list15)
    #print "length of list13",len(list13)

    if(key_with_encryptedstring[-1:]=='+'):
            j=0
            list13[len(list13)-2]=list15[j]
            strr=list15[j+1]+'+'
            list13[len(list13)-1]=strr
    elif(key_with_encryptedstring[-1:]=='*'):
            j=0
            list13[len(list13)-2]=list15[j]
            strr=list15[j+1]+'*'
            list13[len(list13)-1]=strr



    
    key_with_decryptedstring=''
    for j in range(0,len(list13)):
        key_with_decryptedstring=key_with_decryptedstring+list13[j]
    text=key_with_decryptedstring
    i=0
    #print "text",text
    for k in range(0,len(text)-len(string_value1)):
        for j in range(0,len(list1)):
            if(i+2<len(text)):
                if(text[i+2]=='+'):
                    text1=text[i]+text[i+1]+text[i+2]
                    list6.append(text1)
                    i=i+3
                    #print i
                elif(text[i+2]=='*'):
                    text1=text[i]+text[i+1]+text[i+2]
                    list6.append(text1)
                    i=i+3
                    #print i
                elif(text[i+1].islower()):
                    text1=text[i]+text[i+1]
                    list6.append(text1)
                    i=i+2
                elif(text[i]==list1[j]):
                    text1=text[i]
                    list6.append(text1)
                    i=i+1
                    #print i
            elif(i+1<len(text)):
                if(text[i+1].islower()):
                    text1=text[i]+text[i+1]
                    list6.append(text1)
                    i=i+2
                elif(text[i]==list1[j]):
                    text1=text[i]
                    list6.append(text1)
                    i=i+1
                    #print i
            elif(i<len(text)):
                if(text[i]==list1[j]):
                    text1=text[i]
                    list6.append(text1)
                    i=i+1
                    #print i
    #print list6
    cout=0
    for i in range(0,len(list4)):
        if(len(list6[cout])==2):
            spliting=list6[cout+1]
            if(len(spliting)==2):
                first=spliting[0]
                second=spliting[1]
                if(second=='+'):
                    string_value=spliting[:-1]
                    values_decrypt=list1.index(list6[cout])+list1.index(string_value)
                    cout=cout+2
                    #print values_decrypt
                elif(second=='*'):
                    string_value=spliting[:-1]
                    values_decrypt=list1.index(list6[cout])*list1.index(string_value)
                    cout=cout+2
                    #print values_decrypt
                else:
                    values_decrypt=list1.index(list6[cout])
                    cout=cout+1
                    #print values_decrypt
            elif(len(spliting)==3):
                first=spliting[0]
                second=spliting[1]
                third=spliting[2]
                if(third=='+'):
                    string_value=spliting[:-1]
                    values_decrypt=list1.index(list6[cout])+list1.index(string_value)
                    cout=cout+2
                    #print values_decrypt
                elif(third=='*'):
                    string_value=spliting[:-1]
                    values_decrypt=list1.index(list6[cout])*list1.index(string_value)
                    cout=cout+2
                    #print values_decrypt
                else:
                    values_decrypt=list1.index(list6[cout])
                    cout=cout+1
                    #print values_decrypt
            elif(len(spliting)==1):
                values_decrypt=list1.index(list6[cout])
                cout=cout+1
                #print values_decrypt
        elif(len(list6[cout])==1):
            values_decrypt=list1.index(list6[cout])
            cout=cout+1
            #print values_decrypt
        list8.append(values_decrypt)
        #print "cout",cout
    #print "list8",list8
    #print "list3",list3
    #print "list10",list10
    #print len(list3)
    print len(list8)
    for tt in range(0,len(list8)):
        list9.append((list8[tt]*N)/key_message)
    #print list9
    space_values=1+((key_decry_value)/len(list8))
    
    for i in range(0,len(list9)):
        for j in range(0,len(list1)):
            if(list9[i]==j):
                print list1[j]
    #print space_values
    decrypt=''
    list16=[]
    for kkk in range(0,len(list9)/(space_values+1)):
        #print list1[list9[kkk*(space_values+1)]]
        list16.append(list1[list9[kkk*(space_values+1)]])
    for j in range(0,len(list16)):
        decrypt=decrypt+list16[j]
    print decrypt.lower()
    #print list[48];


