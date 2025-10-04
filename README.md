# 👻 I-Ghost Security Module
**Isixhobo Sokuqinisa Ukhuseleko lwe-Windows ne-Azure Esekwe ku-PowerShell**

> **Ukuqinisa ukhuseleko okusebenzayo kwe-endpoints ze-Windows kunye neemeko ze-Azure.** I-Ghost ibonelela ngemisebenzi yokuqinisa esekwe ku-PowerShell enokunceda ukunciphisa ii-vectors zokuhlasela eziqhelekileyo ngokucima iinkonzo kunye neeprotocol ezingafunekiyo.

## ⚠️ Izaziso Ezibalulekileyo

**KUYADINGEKA UKUVAVANYA**: Soloko uvavanya i-Ghost kwiimeko ezingezizo zemveliso kuqala. Ukucima iinkonzo kunokuchaphazela imisebenzi yeshishini esemthethweni.

**AKUKHO SIQINISEKISO**: Nangona i-Ghost ijolise kwii-vectors zokuhlasela eziqhelekileyo, akukho sixhobo sokhuseleko sinokuthintela zonke iinhlaselo. Oku yinxalenye yesicwangciso sokhuseleko esibanzi.

**IMPEMBELELO YOKUSEBENZA**: Eminye imisebenzi inokuchaphazela ukusebenza kwenkqubo. Hlola isicwangciso ngamnye ngononophelo ngaphambi kokusasazwa.

**UVAVANYO LOBUCHULE**: Kwiimeko zemveliso, cebisana neengcali zokhuseleko ukuqinisekisa ukuba izicwangciso zihambelana neemfuno zombutho wakho.

## 📊 Imbonakalo Yokhuseleko

Umonakalo we-ransomware ufikelele **kwi-$57 billion ngo-2025**, uphando lubonisa ukuba uninzi lweenhlaselo eziphumeleleyo zisebenzisa iinkonzo ze-Windows ezisiseko kunye nokucwangciswa okungalunganga. Ii-vectors zokuhlasela eziqhelekileyo ziquka:

- **I-90% yeziganeko ze-ransomware** ziquka ukuxhaphaza i-RDP
- **Ubuthathaka be-SMBv1** benza iinhlaselo ezifana ne-WannaCry ne-NotPetya
- **Ii-macros zamaxwebhu** zihlala ziyindlela ephambili yokuhambisa i-malware
- **Iinhlaselo ezisekelwe kwi-USB** ziyaqhubeka ngokujolisa kwiinethiwekhi ezikude
- **Ukusetyenziswa gwenxa kwe-PowerShell** kuye kwanda kakhulu kwiminyaka yakutshanje

## 🛡️ Imisebenzi Yokhuseleko ye-Ghost

I-Ghost ibonelela **ngemisebenzi eli-16 yokuqinisa i-Windows** kunye **nokudityaniswa kokhuseleko kwe-Azure**:

### Ukuqinisa i-Windows Endpoint

| Umsebenzi | Injongo | Uqwalaselo |
|----------|---------|----------------|
| `Set-RDP` | Ilawula ukufikelela kwe-Remote Desktop | Inokuchaphazela ulawulo olukude |
| `Set-SMBv1` | Ilawula iprotocol ye-SMB yamandulo | Iyadingeka kwiinkqubo ezindala kakhulu |
| `Set-AutoRun` | Ilawula i-AutoPlay/AutoRun | Inokuchaphazela intuthuzelo yomsebenzisi |
| `Set-USBStorage` | Ithintela izixhobo zokugcina i-USB | Inokuchaphazela ukusetyenziswa kwe-USB okusemthethweni |
| `Set-Macros` | Ilawula ukuphumeza i-macro ye-Office | Inokuchaphazela amaxwebhu anamandla e-macro |
| `Set-PSRemoting` | Ilawula i-PowerShell remoting | Inokuchaphazela ulawulo olukude |
| `Set-WinRM` | Ilawula i-Windows Remote Management | Inokuchaphazela ulawulo olukude |
| `Set-LLMNR` | Ilawula iprotocol yokusombulula igama | Ngokuqhelekileyo kukhuselekile ukuyicima |
| `Set-NetBIOS` | Ilawula i-NetBIOS phezu kwe-TCP/IP | Inokuchaphazela usetyenziso lwamandulo |
| `Set-AdminShares` | Ilawula ukwabelana ngolawulo | Inokuchaphazela ukufikelela iifayile ezikude |
| `Set-Telemetry` | Ilawula ukuqokelelwa kwedatha | Inokuchaphazela amandla okuxilonga |
| `Set-GuestAccount` | Ilawula i-akhawunti yendwendwe | Ngokuqhelekileyo kukhuselekile ukuyicima |
| `Set-ICMP` | Ilawula iimpendulo ze-ping | Inokuchaphazela ukuxilonga kwinethiwekhi |
| `Set-RemoteAssistance` | Ilawula i-Remote Assistance | Inokuchaphazela imisebenzi yedesika yoncedo |
| `Set-NetworkDiscovery` | Ilawula ukufumanisa inethiwekhi | Inokuchaphazela ukukhangela inethiwekhi |
| `Set-Firewall` | Ilawula i-Windows Firewall | Ibalulekile kukhuseleko lwenethiwekhi |

### Ukhuseleko lwe-Azure Cloud

| Umsebenzi | Injongo | Iimfuno |
|----------|---------|--------------|
| `Set-AzureSecurityDefaults` | Iyenza kusebenze ukhuseleko lwesiseko lwe-Azure AD | Iimvume ze-Microsoft Graph |
| `Set-AzureConditionalAccess` | Icwangcisa imigaqo-nkqubo yokufikelela | Ilayisenisi ye-Azure AD P1/P2 |
| `Set-AzurePrivilegedUsers` | Iphicothi ii-akhawunti ezineelungelo ezikhethekileyo | Iimvume ze-Global Admin |

### Iinketho Zokusasazwa Kweshishini

| Indlela | Usetyenziso | Iimfuno |
|--------|----------|--------------|
| **Ukwenziwa Ngqo** | Ukuvavanya, iimeko ezincinci | Amalungelo e-admin yasekuhlaleni |
| **Group Policy** | Iimeko zedomain | I-admin yedomain, ulawulo lwe-GP |
| **Microsoft Intune** | Izixhobo ezilawulwa yi-cloud | Ilayisenisi ye-Intune, Graph API |

## 🚀 Ukuqala Ngokukhawuleza

### Uvavanyo Lokhuseleko
```powershell
# Layisha i-module ye-Ghost
IEX(Invoke-WebRequest 'https://raw.githubusercontent.com/jimrtyler/Ghost/main/Ghost.ps1')

# Jonga imeko yokhuseleko yangoku
Get-Ghost
```

### Ukuqinisa Okusisiseko (Vavanya Kuqala)
```powershell
# Ukuqinisa okubalulekileyo - vavanya kwimeko yelebhu kuqala
Set-Ghost -SMBv1 -AutoRun -Macros

# Hlola utshintsho
Get-Ghost
```

### Ukusasazwa Kweshishini
```powershell
# Ukusasazwa kwe-Group Policy (iimeko zedomain)
Set-Ghost -SMBv1 -AutoRun -GroupPolicy

# Ukusasazwa kwe-Intune (izixhobo ezilawulwa yi-cloud)
Set-Ghost -SMBv1 -RDP -USBStorage -Intune
```

## 📋 Iindlela Zokufakela

### Inketho 1: Ukukhuphela Ngqo (Ukuvavanya)
```powershell
IEX(Invoke-WebRequest 'https://raw.githubusercontent.com/jimrtyler/Ghost/main/Ghost.ps1')
```

### Inketho 2: Ukufakela i-Module
```powershell
# Faka ukusuka kwi-PowerShell Gallery (xa ifumaneka)
Install-Module Ghost -Scope CurrentUser
Import-Module Ghost
```

### Inketho 3: Ukusasazwa Kweshishini
```powershell
# Kopa kwindawo yenethiwekhi ukuze usasaze i-Group Policy
# Cwangcisa izikripti ze-PowerShell ze-Intune ukuze usasaze i-cloud
```

## 💼 Imizekelo Yokusetyenziswa

### Ishishini Elincinci
```powershell
# Ukhuseleko olususeleko kunye nefuthe elincinci
Set-Ghost -SMBv1 -AutoRun -Macros -ICMP
```

### Imeko Yezempilo
```powershell
# Ukuqinisa okugxile kwi-HIPAA
Set-Ghost -SMBv1 -RDP -USBStorage -AdminShares -Telemetry
```

### Iinkonzo Zemali
```powershell
# Ukucwangciswa kokhuseleko oluphezulu
Set-Ghost -RDP -SMBv1 -AutoRun -USBStorage -Macros -PSRemoting -AdminShares
```

### Umbutho Oqala Nge-Cloud
```powershell
# Ukusasazwa okulawulwa yi-Intune
Connect-IntuneGhost -Interactive
Set-Ghost -SMBv1 -RDP -AutoRun -Macros -Intune
```

## 🔍 Iinkcukacha Zemisebenzi

### Imisebenzi Yokuqinisa Esisiseko

#### Iinkonzo Zenethiwekhi
- **RDP**: Ithintela ukufikelela i-desktop ekude okanye yenza i-port ibe ngokungacwangciswanga
- **SMBv1**: Icima iprotocol yokwabelana ngefayile yamandulo
- **ICMP**: Ithintela iimpendulo ze-ping zokuhlola
- **LLMNR/NetBIOS**: Ithintela iiprotocol zokusombulula igama zamandulo

#### Ukhuseleko Lwenkqubo
- **Macros**: Icima ukuphumeza i-macro kwizicelo ze-Office
- **AutoRun**: Ithintela ukuphumeza okuzenzekelayo kumajelo asusekayo

#### Ulawulo Olukude
- **PSRemoting**: Icima iiseshoni ze-PowerShell ezikude
- **WinRM**: Imisa i-Windows Remote Management
- **Remote Assistance**: Ithintela unxibelelwano lwe-Remote Assistance

#### Ulawulo Lokufikelela
- **Admin Shares**: Icima ukwabelana nge-C$, ADMIN$
- **Guest Account**: Icima ukufikelela kwe-akhawunti yendwendwe
- **USB Storage**: Ithintela ukusetyenziswa kwesixhobo se-USB

### Ukudityaniswa kwe-Azure
```powershell
# Nxulumanisa ne-tenant ye-Azure
Connect-AzureGhost -Interactive

# Yenza kusebenze izinto ezingagqibekanga zokhuseleko
Set-AzureSecurityDefaults -Enable

# Cwangcisa ukufikelela okuxhomekeke kwiimeko
Set-AzureConditionalAccess -BlockLegacyAuth -RequireMFA

# Phicothi abasebenzisi abaneelungelo ezikhethekileyo
Set-AzurePrivilegedUsers -AuditOnly
```

### Ukudityaniswa kwe-Intune (Ukutsha kwi-v2)
```powershell
# Nxulumanisa ne-Intune
Connect-IntuneGhost -Interactive

# Sasaza ngokusebenzisa imigaqo-nkqubo ye-Intune
Set-IntuneGhost -Settings @{
    RDP = $true
    SMBv1 = $true
    USBStorage = $true
    Macros = $true
}
```

## ⚠️ Uqwalaselo Olubalulekileyo

### Iimfuno Zokuvavanya
- **Imeko Yelebhu**: Vavanya zonke izicwangciso kwimeko eyahlukileyo kuqala
- **Ukusasazwa Ngezigaba**: Sasaza kancinci kancinci ukuze uchonge iingxaki
- **Isicwangciso Sokubuyela Umva**: Qinisekisa ukuba unokubuyisela utshintsho xa kuyimfuneko
- **Amaxwebhu**: Rekoda ukuba zeziphi izicwangciso ezisebenza kwimeko yakho

### Ifuthe Elinokubakho
- **Imveliso Yomsebenzisi**: Ezinye izicwangciso zinokuchaphazela ukuhamba komsebenzi wemihla ngemihla
- **Izicelo Zamandulo**: Iinkqubo ezindala zisenokufuna iiprotocol ezithile
- **Ukufikelela Okukude**: Qwalasela ifuthe kulawulo lwasemthethweni olukude
- **Iinkqubo Zeshishini**: Qinisekisa ukuba izicwangciso aziphuli imisebenzi ebalulekileyo

### Imida Yokhuseleko
- **Ukhuseleko Olunzulu**: I-Ghost yinqanaba elinye lokhuseleko, ayisosisombululo esipheleleyo
- **Ulawulo Oluqhubekayo**: Ukhuseleko lufuna ukubek'esweni okuqhubekayo kunye nohlaziyo
- **Uqeqesho Lomsebenzisi**: Ulawulo lobugcisa kufuneka ludityaniswe nolwazi lokhuseleko
- **Ukuguquka Kwengozi**: Iindlela ezintsha zokuhlasela zinokudlula ukhuseleko lwangoku

## 🎯 Imizekelo Yeemeko Zohlaselo

Nangona i-Ghost ijolise kwii-vectors zokuhlasela eziqhelekileyo, uthintelo oluthile luxhomekeke ekuphunyezweni okulungileyo nakuvavanyeni:

### Iinhlaselo Zohlobo lwe-WannaCry
- **Ukunciphisa**: `Set-Ghost -SMBv1` icima iprotocol esengozini
- **Uqwalaselo**: Qinisekisa ukuba akukho nkqubo yamandulo efuna i-SMBv1

### I-Ransomware Esekwe kwi-RDP
- **Ukunciphisa**: `Set-Ghost -RDP` ithintela ukufikelela i-desktop ekude
- **Uqwalaselo**: Iindlela ezinye zokufikelela kude zisenokufuneka

### I-Malware Esekwe Emaxwebhini
- **Ukunciphisa**: `Set-Ghost -Macros` icima ukuphumeza i-macro
- **Uqwalaselo**: Inokuchaphazela amaxwebhu asemthethweni anamandla e-macro

### Izoyikiso Ezihanjiswa nge-USB
- **Ukunciphisa**: `Set-Ghost -USBStorage -AutoRun` ithintela ukusebenza kwe-USB
- **Uqwalaselo**: Inokuchaphazela ukusetyenziswa kwesixhobo se-USB esisemthethweni

## 🏢 Iimpawu Zeshishini

### Inkxaso ye-Group Policy
```powershell
# Sebenzisa izicwangciso ngokusebenzisa i-registry ye-Group Policy
Set-Ghost -SMBv1 -RDP -AutoRun -GroupPolicy

# Izicwangciso zisetyenziswa kwi-domain yonke emva kokuhlaziywa kwe-GP
gpupdate /force
```

### Ukudityaniswa kwe-Microsoft Intune
```powershell
# Dala imigaqo-nkqubo ye-Intune yezicwangciso ze-Ghost
Set-IntuneGhost -Settings $GhostSettings -Interactive

# Imigaqo-nkqubo isasazwa ngokuzenzekelayo kwizixhobo ezilawulwayo
```

### Ingxelo Yokuhambelana
```powershell
# Dala ingxelo yovavanyo lokhuseleko
Get-Ghost | Export-Csv -Path "SecurityAudit-$(Get-Date -Format 'yyyy-MM-dd').csv"

# Ingxelo yemeko yokhuseleko ye-Azure
Get-AzureGhost | Out-File "AzureSecurityReport.txt"
```

## 📚 Iindlela Ezilungileyo

### Ngaphambi Kokusasazwa
1. **Bhala Imeko Yangoku**: Sebenzisa `Get-Ghost` ngaphambi kotshintsho
2. **Vavanya Ngokupheleleyo**: Qinisekisa kwimeko engeyiyo yemveliso
3. **Dala Isicwangciso Sokubuyela Umva**: Yazi indlela yokubuyisela isicwangciso ngasinye
4. **Uphononongo Lwabathathi-nxaxheba**: Qinisekisa ukuba iiyunithi zeshishini zivuma utshintsho

### Ngexesha Lokusasazwa
1. **Indlela Yezigaba**: Sasaza kuqala kumaqela e-pilot
2. **Bek'esweni Ifuthe**: Jonga izikhalazo zabasebenzisi okanye iingxaki zenkqubo
3. **Bhala Iingxaki**: Rekoda nayiphi na ingxaki ukuze uhlale uyikhumbula
4. **Nxibelelana Ngotshintsho**: Yazisa abasebenzisi malunga nophuculo lokhuseleko

### Emva Kokusasazwa
1. **Uvavanyo Rhoqo**: Sebenzisa `Get-Ghost` ngamaxesha athile ukuze uqinisekise izicwangciso
2. **Hlaziya Amaxwebhu**: Gcina ukucwangciswa kokhuseleko kuhlaziyiwe
3. **Hlola Ukusebenza Kakuhle**: Bek'esweni iziganeko zokhuseleko
4. **Uphuculo Oluqhubekayo**: Lungelelanisa izicwangciso ngokusekwe kwimbonakalo yengozi

## 🔧 Ukulungisa Iingxaki

### Iingxaki Eziqhelekileyo
- **Iimpazamo Zemvume**: Qinisekisa iseshoni ye-PowerShell ephakanyisiweyo
- **Ukuxhomekeka Kweenkonzo**: Ezinye iinkonzo zisenokuba nokuxhomekeka
- **Ukuhambelana Kwenkqubo**: Vavanya ngezicelo zeshishini
- **Unxibelelwano Lwenethiwekhi**: Qinisekisa ukuba ukufikelela okukude kusasebenza

### Iinketho Zokubuyisela
```powershell
# Vula kwakhona iinkonzo ezithile xa kuyimfuneko
Set-RDP -Enable
Set-SMBv1 -Enable
Set-AutoRun -Enable
Set-Macros -Enable
```

## 👨‍💻 Malunga Nombhali

**Jim Tyler** - I-Microsoft MVP ye-PowerShell
- **YouTube**: [@PowerShellEngineer](https://youtube.com/@PowerShellEngineer) (10,000+ ababhalisileyo)
- **I-Newsletter**: [PowerShell.News](https://powershell.news) - Ubukrelekrele bokhuseleko beveki ngeveki
- **Umbhali**: "PowerShell for Systems Engineers"
- **Amava**: Amashumi eminyaka we-automation ye-PowerShell kunye nokhuseleko lwe-Windows

## 📄 Ilayisenisi Nesaziso

### Ilayisenisi ye-MIT
I-Ghost ibonelelwa phantsi kwelayisenisi ye-MIT yokusetyenziswa kwasimahla, uguqulelo, kunye nokusasazwa.

### Isaziso Sokhuseleko
- **Akukho Siqinisekiso**: I-Ghost ibonelelwa "njengoko injalo" ngaphandle kwaso nasiphi na isiqinisekiso
- **Ukuvavanya Kuyadingeka**: Soloko uvavanya kwiimeko ezingezizo zemveliso kuqala
- **Isikhokelo Sobungcali**: Ukusasazwa kwemveliso, cebisana neengcali zokhuseleko
- **Ifuthe Lokusebenza**: Ababhali abatyalwa batyala nangaluphi na uphazamiseko
- **Ukhuseleko Olubanzi**: I-Ghost yinxalenye yesicwangciso sokhuseleko esipheleleyo

### Inkxaso
- **Iingxaki ze-GitHub**: [Xela iziphene okanye ucele iimpawu](https://github.com/jimrtyler/Ghost/issues)
- **Amaxwebhu**: Sebenzisa `Get-Help <function> -Full` ukufumana uncedo olubanzi
- **Uluntu**: Iiforum zoluntu lwe-PowerShell nezokhuseleko

---

**🔒 Qinisa imeko yakho yokhuseleko nge-Ghost - kodwa soloko uvavanya kuqala.**

```powershell
# Qala ngovavanyo, kungekhona ngokuqikelela
Get-Ghost
```

**⭐ Ukuba i-Ghost inceda ukuphucula imeko yakho yokhuseleko, nika le repository inkwenkwezi!**