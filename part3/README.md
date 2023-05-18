# BGU 
## Accuracy for the highest prob form (top-1)
POLISH: 0.73  
ESTONIAN: 0.55  
FINNISH: 0.44  
  
## Pearson's correlation
Correlation for the probabilities of the forms predicted by the model and the ones from children's data (if they match)  
POLISH (134/150 forms): -0.02735669  
ESTONIAN (121/144 forms): 0.54783086  
FINNISH (134/162): 0.46281223 

On All forms (assigning zero probability for the cases where the correct form is not in top-10):  
POLISH (150): 0.23111538    
ESTONIAN (144): 0.57870074  
FINNISH (162): 0.46264211


## Cosine Similarity for predicted probabilties
POLISH (134/150 forms): 0.99  
ESTONIAN (121/144 forms): 0.99  
FINNISH (134/162): 0.98  

On All forms (assigning zero probability for the cases where the correct form is not in top-10):  
POLISH: 0.94  
ESTONIAN: 0.94    
FINNISH: 0.92  

## Forms that didn't have any correct prediction in top-10
POLISH
```
No correct prediction for: ['aparat', 'DAT', 'aparatowi', 'aparat', 'aparatɔvi']
No correct prediction for: ['bocian', 'DAT', 'bocianowi', 'bɔt͡ɕan', 'bɔt͡ɕanɔvi']
No correct prediction for: ['chleb', 'DAT', 'chlebowi', 'xlɛp', 'xlɛbɔvi']
No correct prediction for: ['doktor', 'DAT', 'doktorowi', 'dɔktɔr', 'dɔktɔrɔvi']
No correct prediction for: ['dźwig', 'DAT', 'dźwigowi', 'd͡ʑvik', 'd͡ʑvigɔvi']
No correct prediction for: ['grzebień', 'DAT', 'grzbieniowi', 'gʒɛbjɛɲ', 'gʒbjɛɲɔvi']
No correct prediction for: ['koło', 'DAT', 'kołu', 'kɔwɔ', 'kɔwu']
No correct prediction for: ['ołówek', 'DAT', 'ołówkowi', 'ɔwuvɛk', 'ɔwufkɔvi']
No correct prediction for: ['pociąg', 'DAT', 'pociągowi', 'pɔt͡ɕɔ̃ŋk', 'pɔt͡ɕɔ̃ŋgɔvi']
No correct prediction for: ['samochód', 'DAT', 'samochodowi', 'samɔxut', 'samɔxɔdɔvi']
No correct prediction for: ['słoik', 'DAT', 'słoikowi', 'swɔik', 'swɔikɔvi']
No correct prediction for: ['smok', 'DAT', 'smokowi', 'smɔk', 'smɔkɔvi']
No correct prediction for: ['telefon', 'DAT', 'telefonowi', 'tɛlɛfɔn', 'tɛlɛfɔnɔvi']
No correct prediction for: ['traktor', 'DAT', 'traktorowi', 'traktɔr', 'traktɔrɔvi']
No correct prediction for: ['wieloryb', 'ACC', 'wieloryba', 'vjɛlɔrɨp', 'vjɛlɔrɨba']
No correct prediction for: ['wieloryb', 'DAT', 'wielorybowi', 'vjɛlɔrɨp', 'vjɛlɔrɨbɔvi']
```

ESTONIAN
```
No correct prediction for: ['hobune', 'PAR', 'hobust', 'hobune', 'hobust']
No correct prediction for: ['nuga', 'GEN', 'noa', 'nugɑ', 'noɑ']
No correct prediction for: ['nuga', 'COM', 'noaga', 'nugɑ', 'noɑgɑ']
No correct prediction for: ['nuga', 'ALL', 'noale', 'nugɑ', 'noɑle']
No correct prediction for: ['nuga', 'INE', 'noas', 'nugɑ', 'noɑs']
No correct prediction for: ['nuga', 'ELA', 'noast', 'nugɑ', 'noɑst']
No correct prediction for: ['päike', 'ALL', 'päikesele', 'pæike', 'pæikesele']
No correct prediction for: ['ratas', 'GEN', 'ratta', 'rɑtɑs', 'rɑt;ɑ']
No correct prediction for: ['ratas', 'COM', 'rattaga', 'rɑtɑs', 'rɑt;ɑgɑ']
No correct prediction for: ['ratas', 'ALL', 'rattale', 'rɑtɑs', 'rɑt;ɑle']
No correct prediction for: ['ratas', 'INE', 'rattas', 'rɑtɑs', 'rɑt;ɑs']
No correct prediction for: ['ratas', 'ELA', 'rattast', 'rɑtɑs', 'rɑt;ɑst']
No correct prediction for: ['saabas', 'GEN', 'saapa', 'sɑːbɑs', 'sɑ;pɑ']
No correct prediction for: ['saabas', 'COM', 'saapaga', 'sɑːbɑs', 'sɑ;pɑgɑ']
No correct prediction for: ['saabas', 'ALL', 'saapale', 'sɑːbɑs', 'sɑ;pɑle']
No correct prediction for: ['saabas', 'INE', 'saapas', 'sɑːbɑs', 'sɑ;pɑs']
No correct prediction for: ['saabas', 'ELA', 'saapast', 'sɑːbɑs', 'sɑ;pɑst']
No correct prediction for: ['tigu', 'GEN', 'teo', 'tigu', 'teo']
No correct prediction for: ['tigu', 'COM', 'teoga', 'tigu', 'teogɑ']
No correct prediction for: ['tigu', 'ALL', 'teole', 'tigu', 'teole']
No correct prediction for: ['tigu', 'INE', 'teos', 'tigu', 'teos']
No correct prediction for: ['tigu', 'ELA', 'teost', 'tigu', 'teost']
No correct prediction for: ['tuba', 'GEN', 'toa', 'tubɑ', 'toɑ']
```

FINNISH
```
No correct prediction for: ['aarre', 'ALL', 'aarteelle', 'ɑːrːe', 'ɑːrteːlːe']
No correct prediction for: ['aarre', 'ILL', 'aarteeseen', 'ɑːrːe', 'ɑːrteːseːn']
No correct prediction for: ['allas', 'ALL', 'altaalle', 'ɑlːɑs', 'ɑltɑːlːe']
No correct prediction for: ['allas', 'GEN', 'altaan', 'ɑlːɑs', 'ɑltɑːn']
No correct prediction for: ['allas', 'ILL', 'altaaseen', 'ɑlːɑs', 'ɑltɑːseːn']
No correct prediction for: ['allas', 'INE', 'altaassa', 'ɑlːɑs', 'ɑltɑːsːɑ']
No correct prediction for: ['allas', 'ELA', 'altaasta', 'ɑlːɑs', 'ɑltɑːstɑ']
No correct prediction for: ['avain', 'ALL', 'avaimelle', 'ɑʋɑin', 'ɑʋɑimelːe']
No correct prediction for: ['avain', 'INE', 'avaimessa', 'ɑʋɑin', 'ɑʋɑimesːɑ']
No correct prediction for: ['avain', 'ELA', 'avaimesta', 'ɑʋɑin', 'ɑʋɑimestɑ']
No correct prediction for: ['hai', 'ILL', 'haihin', 'hɑi', 'hɑihin']
No correct prediction for: ['hevonen', 'PAR', 'hevosta', 'heʋonen', 'heʋostɑ']
No correct prediction for: ['kaulin', 'ALL', 'kaulimelle', 'kɑulin', 'kɑulimelːe']
No correct prediction for: ['kiuas', 'ALL', 'kiukaalle', 'kiuɑs', 'kiukɑːlːe']
No correct prediction for: ['kiuas', 'GEN', 'kiukaan', 'kiuɑs', 'kiukɑːn']
No correct prediction for: ['kiuas', 'ILL', 'kiukaaseen', 'kiuɑs', 'kiukɑːseːn']
No correct prediction for: ['kiuas', 'INE', 'kiukaassa', 'kiuɑs', 'kiukɑːsːɑ']
No correct prediction for: ['kiuas', 'ELA', 'kiukaasta', 'kiuɑs', 'kiukɑːstɑ']
No correct prediction for: ['lapanen', 'PAR', 'lapasta', 'lɑpɑnen', 'lɑpɑstɑ']
No correct prediction for: ['lautanen', 'PAR', 'lautasta', 'lɑutɑnen', 'lɑutɑstɑ']
No correct prediction for: ['puu', 'ILL', 'puuhun', 'puː', 'puːhun']
No correct prediction for: ['rengas', 'ALL', 'renkaalle', 'reŋːɑs', 'reŋkɑːlːe']
No correct prediction for: ['rengas', 'GEN', 'renkaan', 'reŋːɑs', 'reŋkɑːn']
No correct prediction for: ['rengas', 'ILL', 'renkaaseen', 'reŋːɑs', 'reŋkɑːseːn']
No correct prediction for: ['rengas', 'INE', 'renkaassa', 'reŋːɑs', 'reŋkɑːsːɑ']
No correct prediction for: ['rengas', 'ELA', 'renkaasta', 'reŋːɑs', 'reŋkɑːstɑ']
No correct prediction for: ['sormus', 'ELA', 'sormusksesta', 'sormus', 'sormusksestɑ']
No correct prediction for: ['vyö', 'ILL', 'vyöhön', 'ʋyø', 'ʋyøhøn']
```
