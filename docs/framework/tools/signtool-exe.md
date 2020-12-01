---
title: SignTool.exe (Signaturtool)
description: Erfahren Sie mehr über „SignTool.exe“, das Signaturtool. Dieses Befehlszeilentool signiert Dateien digital, überprüft Signaturen in Dateien und fügt Dateien Zeitstempel hinzu.
ms.date: 03/30/2017
helpviewer_keywords:
- Sign tool
- SignTool.exe
ms.assetid: 0c25ff6c-bff3-422e-b017-146a3ee86cb9
ms.openlocfilehash: 46a7453ff7de0329d9cd7f671dcaa0a3e3e0e54c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238469"
---
# <a name="signtoolexe-sign-tool"></a>SignTool.exe (Signaturtool)

Beim Signierungstool handelt es sich um ein Befehlszeilentool, das Dateien digital signiert, Signaturen in Dateien überprüft und Dateien Zeitstempel hinzufügt.  
  
 Dieses Tool wird automatisch mit Visual Studio installiert. Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).

> [!Note]  
> Das Windows 10 SDK, Windows 10 HLK, Windows 10 WDK und Windows 10 ADK ab **Build 20236** erfordern die Angabe des Digestalgorithmus. Der SignTool-Befehl `sign` erfordert die Angabe der Option für den **Digestalgorithmus für Dateien** `/fd` und den **Digestalgorithmus für Zeitstempel** `/td` während der Erstellung von Signaturen bzw. Zeitstempeln. Eine Warnung (anfänglich Fehlercode 0) wird ausgelöst, wenn `/fd` beim Erstellen der Signatur und `/td` beim Erstellen des Zeitstempels nicht angegeben wird. In späteren Versionen von SignTool wird aus dieser Warnung ein Fehler. SHA256 wird empfohlen und gilt in der Branche als sicherer als SHA1.  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```console  
signtool [command] [options] [file_name | ...]  
```  
  
## <a name="parameters"></a>Parameter  
  
|Argument|BESCHREIBUNG|  
|--------------|-----------------|  
|`command`|Einer von vier Befehlen (`catdb`, `sign`, `Timestamp` oder `Verify`), der einen für eine Datei auszuführenden Vorgang angibt. In der folgenden Tabelle finden Sie eine Beschreibung der einzelnen Befehle.|  
|`options`|Eine Option, die einen Befehl ändert. Neben der globalen `/q`-Option und `/v`-Option wird von jedem Befehl ein eindeutiger Satz von Optionen unterstützt.|  
|`file_name`|Der Pfad zu einer zu signierenden Datei.|  
  
 Vom Signierungstool werden die folgenden Befehle unterstützt. Jeder Befehl wird mit einem unterschiedlichem Satz von Optionen verwendet, die in den jeweiligen Abschnitten aufgeführt sind.  
  
|Get-Help|Beschreibung|  
|-------------|-----------------|  
|`catdb`|Fügt einer Katalogdatenbank eine Katalogdatei hinzu oder entfernt sie daraus. Katalogdatenbanken werden für die automatische Suche von Katalogdateien verwendet und mit einer GUID gekennzeichnet. Eine Liste der vom `catdb`-Befehl unterstützten Optionen finden Sie unter [catdb-Befehlsoptionen](signtool-exe.md#catdb).|  
|`sign`|Signiert Dateien digital. Digitale Signaturen schützen Dateien vor Manipulationen und ermöglichen es Benutzern, den Signaturgeber anhand eines Signaturzertifikats zu überprüfen. Eine Liste der vom `sign`-Befehl unterstützten Optionen finden Sie unter [sign-Befehlsoptionen](signtool-exe.md#sign).|  
|`Timestamp`|Fügt Dateien Timestamps hinzu. Eine Liste der vom `TimeStamp`-Befehl unterstützten Optionen finden Sie unter [TimeStamp-Befehlsoptionen](signtool-exe.md#TimeStamp).|  
|`Verify`|Überprüft die digitale Signatur von Dateien, indem ermittelt wird, ob das Signaturzertifikat von einer vertrauenswürdigen Zertifizierungsstelle ausgestellt wurde, ob das Signaturzertifikat widerrufen wurde, und (optional) ob das Signaturzertifikat für eine bestimmte Richtlinie gültig ist. Eine Liste der vom `Verify`-Befehl unterstützten Optionen finden Sie unter [Verify-Befehlsoptionen](signtool-exe.md#Verify).|  
  
 Die folgenden Optionen gelten für alle Signierungstoolbefehle.  
  
|Globale Option|Beschreibung|  
|-------------------|-----------------|  
|**/q**|Bei erfolgreicher Ausführung des Befehls erfolgt keine Ausgabe, bei einen Fehler werden minimale Daten ausgegeben|  
|**/v**|Zeigt unabhängig von der erfolgreichen Ausführung des Befehls eine ausführliche Ausgabe und Warnmeldungen an.|  
|**/debug**|Zeigt Debuginformationen an.|  
  
<a name="catdb"></a>

## <a name="catdb-command-options"></a>catdb-Befehlsoptionen  

 In der folgenden Tabelle werden die Optionen aufgeführt, die mit dem `catdb`-Befehl verwendet werden können.  
  
|Catdb-Option|Beschreibung|  
|------------------|-----------------|  
|`/d`|Gibt an, dass die Standardkatalogdatenbank aktualisiert wird. Wenn weder die `/d`-Option noch die `/g`-Option verwendet wird, führt das Signierungstool ein Update der Systemkomponenten- und Treiberdatenbank aus.|  
|`/g` *GUID*|Gibt an, dass die durch die *GUID* (Globally Unique Identifier) bezeichnete Katalogdatenbank aktualisiert wird.|  
|`/r`|Entfernt die angegebenen Kataloge aus der Katalogdatenbank. Wenn diese Option nicht angegeben wird, fügt das Signierungstool der Katalogdatenbank die angegebenen Kataloge hinzu.|  
|`/u`|Gibt an, dass automatisch ein eindeutiger Name für die hinzugefügten Katalogdateien generiert wird. Ggf. werden die Katalogdateien umbenannt, um Namenskonflikte mit vorhandenen Katalogdateien zu verhindern. Wenn diese Option nicht angegeben wird, werden vorhandene Kataloge vom Signierungstool mit gleichnamigen hinzuzufügenden Katalogen überschrieben.|  
  
<a name="sign"></a>

## <a name="sign-command-options"></a>sign-Befehlsoptionen  

 In der folgenden Tabelle werden die Optionen aufgeführt, die mit dem `sign`-Befehl verwendet werden können.  
  
|Sign-Befehlsoption|Beschreibung|  
|-------------------------|-----------------|  
|`/a`|Wählt automatisch das beste Signaturzertifikat aus. Das Signierungstool findet alle gültigen Zertifikate, die sämtliche angegebenen Bedingungen erfüllen, und wählt das Zertifikat mit der längsten Gültigkeitsdauer aus. Wenn diese Option nicht vorhanden ist, wird vom Signierungstool nur ein bestehendes gültiges Signaturzertifikat erwartet.|  
|`/ac`  *file*|Fügt dem Signaturblock ein zusätzliches Zertifikat aus *file* hinzu.|  
|`/as`|Fügt diese Signatur an. Wenn keine Primärsignatur vorhanden ist, wird diese Signatur stattdessen zur Primärsignatur.|  
|`/c`  *CertTemplateName*|Gibt den Zertifikatsvorlagennamen (eine Microsoft-Erweiterung) für das Signaturzertifikat an.|  
|`/csp`  *CSPName*|Gibt den Kryptografiedienstanbieter (CSP) an, der den privaten Schlüsselcontainer enthält.|  
|`/d`  *Desc*|Gibt eine Beschreibung des signierten Inhalts an.|  
|`/du`  *URL*|Gibt eine URL (Uniform Resource Locator) für die erweiterte Beschreibung des signierten Inhalts an.|  
|`/f`  *SignCertFile*|Gibt das Signaturzertifikat in einer Datei an. Wenn die Datei im PFX-Format (Personal Information Exchange) vorliegt und mit einem Kennwort gesichert ist, verwenden Sie zur Angabe des Kennworts die `/p`-Option. Wenn die Datei keine privaten Schlüssel aufweist, verwenden Sie die `/csp`-Option und `/kc`-Option, um den CSP-Namen und den Namen des privaten Schlüsselcontainers anzugeben.|  
|`/fd`|Gibt den Dateihashwertalgorithmus zum Erstellen von Dateisignaturen an. </br> **Hinweis**: Eine Warnung wird generiert, wenn beim Erstellen der Signatur der Schalter `/fd` nicht angegeben wird. Der Standardalgorithmus ist zwar SHA1, aber SHA256 wird empfohlen.|
|`/fd` *certHash*|Durch Angabe der Zeichenfolge *certHash* wird standardmäßig der auf dem Signaturzertifikat verwendete Algorithmus verwendet. </br> **Hinweis**: Nur in Windows 10 Kit-Builds 20236 und höher verfügbar.|  
|`/i`  *IssuerName*|Gibt den Namen des Ausstellers des Signaturzertifikats an. Dieser Wert kann eine Teilzeichenfolge des gesamten Ausstellernamens sein.|  
|`/kc`  *PrivKeyContainerName*|Gibt den Namen des privaten Schlüsselcontainers an.|  
|`/n`  *SubjectName*|Gibt den Namen des Antragstellers des Signaturzertifikats an. Dieser Wert kann eine Teilzeichenfolge des gesamten Antragstellernamens sein.|  
|`/nph`|Wenn unterstützt, werden Seitenhashes für ausführbare Dateien unterdrückt. Die Standardeinstellung wird von der SIGNTOOL_PAGE_HASHES-Umgebungsvariablen und der wintrust.dll-Version bestimmt. Für nicht portable ausführbare Dateien wird diese Option ignoriert.|  
|`/p`  *Password*|Gibt das Kennwort zum Öffnen einer PFX-Datei an. (Verwenden Sie die `/f`-Option, um eine PFX-Datei anzugeben.)|  
|`/p7` *Pfad*|Gibt an, dass für jede ausgewählte Inhaltsdatei eine PKCS #7-Datei (Public Key Cryptography Standards) erstellt wird. PKCS #7-Dateien erhalten die Bezeichnung „*Pfad*\\*Dateiname*.p7“.|  
|`/p7ce` *Value*|Gibt Optionen für den signierten PKCS #7-Inhalt an. Legen Sie *Wert* auf „Embedded“ fest, um den signierten Inhalt in die PKCS #7-Datei einzubetten, oder auf „DetachedSignedData“, um den signierten Datenabschnitt einer getrennten PKCS #7-Datei zu erstellen. Ohne Verwendung der `/p7ce`-Option wird der signierte Inhalt standardmäßig eingebettet.|  
|`/p7co` *\<OID>*|Gibt den Objektbezeichner (OID) zur Identifizierung des signierten PKCS #7-Inhalts an.|  
|`/ph`|Wenn unterstützt, werden Seitenhashes für ausführbare Dateien generiert.|  
|`/r`  *RootSubjectName*|Gibt den Antragstellernamen des Stammzertifikats an, mit dem das Signaturzertifikat verkettet werden muss. Dieser Wert kann eine Teilzeichenfolge des gesamten Antragstellernamens des Stammzertifikats sein.|  
|`/s`  *StoreName*|Gibt den beim Suchen des Zertifikats zu öffnenden Speicher an. Ohne Angabe dieser Option wird der `My`-Speicher geöffnet.|  
|`/sha1`  *Hash*|Gibt den SHA1-Hash des Signaturzertifikats an. In der Regel wird der SHA1-Hash angegeben, wenn die von den verbleibenden Schaltern festgelegten Kriterien von mehreren Zertifikaten erfüllt werden.|  
|`/sm`|Gibt an, dass anstatt eines Benutzerspeichers ein Computerspeicher verwendet wird.|  
|`/t`  *URL*|Gibt die URL des Zeitstempelservers an. Wenn diese Option (oder `/tr`) nicht vorhanden ist, wird der signierten Datei kein Zeitstempel hinzugefügt. Im Fall eines Fehlers beim Hinzufügen des Zeitstempels wird eine Warnung generiert. Diese Option kann nicht mit der `/tr`-Option verwendet werden.|  
|`/td`  *alg*|Wird mit der `/tr`-Option zum Anfordern eines vom RFC 3161-Zeitstempelserver verwendeten Digestalgorithmus genutzt. </br> **Hinweis**: Eine Warnung wird generiert, wenn beim Erstellen des Zeitstempels der Schalter `/td` nicht angegeben wird. Der Standardalgorithmus ist zwar SHA1, aber SHA256 wird empfohlen. <br/> Der Schalter `/td` muss nach und nicht vor dem Schalter `/tr` deklariert werden. Wenn der Schalter `/td` vor dem Schalter `/tr` deklariert wird, stammt der zurückgegebene Zeitstempel vom SHA1-Algorithmus und nicht vom gewünschten SHA256-Algorithmus. |
|`/tr`  *URL*|Gibt die URL des RFC 3161-Zeitstempelservers an. Wenn diese Option (oder `/t`) nicht vorhanden ist, wird der signierten Datei kein Zeitstempel hinzugefügt. Im Fall eines Fehlers beim Hinzufügen des Zeitstempels wird eine Warnung generiert. Diese Option kann nicht mit der `/t`-Option verwendet werden.|
|`/u`  *Usage*|Gibt die verbesserte Schlüsselverwendung (EKU) an, die im Signaturzertifikat vorhanden sein muss. Der Verwendungswert kann durch einen OID oder eine Zeichenfolge angegeben werden. Die Standardverwendung lautet "Codesignatur" (1.3.6.1.5.5.7.3.3).|  
|`/uw`|Gibt die Verwendung von "Verifizierung von Windows-Systemkomponenten" (1.3.6.1.4.1.311.10.3.6) an.|  
  
 Verwendungsbeispiele finden Sie unter [Using SignTool to Sign a File (Signieren einer Datei mit SignTool)](/windows/desktop/SecCrypto/using-signtool-to-sign-a-file).  
  
<a name="TimeStamp"></a>

## <a name="timestamp-command-options"></a>TimeStamp-Befehlsoptionen  

 In der folgenden Tabelle werden die Optionen aufgeführt, die mit dem `TimeStamp`-Befehl verwendet werden können.  
  
|TimeStamp-Option|Beschreibung|  
|----------------------|-----------------|  
|`/p7`|Fügt PKCS #7-Dateien Zeitstempel hinzu.|  
|`/t`  *URL*|Gibt die URL des Zeitstempelservers an. Vor dem Hinzufügen eines Zeitstempels muss die jeweilige Datei signiert werden. Entweder die `/t`-Option oder die `/tr`-Option ist erforderlich.|  
|`/td`  *alg*|Wird mit der `/tr`-Option zum Anfordern eines vom RFC 3161-Zeitstempelserver verwendeten Digestalgorithmus genutzt. </br> **Hinweis**: Eine Warnung wird generiert, wenn beim Erstellen des Zeitstempels der Schalter `/td` nicht angegeben wird. Der Standardalgorithmus ist zwar SHA1, aber SHA256 wird empfohlen. <br/> Der Schalter `/td` muss nach und nicht vor dem Schalter `/tr` deklariert werden. Wenn der Schalter `/td` vor dem Schalter `/tr` deklariert wird, stammt der zurückgegebene Zeitstempel vom SHA1-Algorithmus und nicht vom gewünschten SHA256-Algorithmus. |
|`/tp` *index*|Fügt der Signatur bei *Index* einen Zeitstempel hinzu|  
|`/tr`  *URL*|Gibt die URL des RFC 3161-Zeitstempelservers an. Vor dem Hinzufügen eines Zeitstempels muss die jeweilige Datei signiert werden. Entweder die `/tr`-Option oder die `/t`-Option ist erforderlich.|  
  
 Ein Verwendungsbeispiel finden Sie unter [Adding Time Stamps to Previously Signed Files (Hinzufügen von Zeitstempeln zu bereit signierten Dateien)](/windows/desktop/SecCrypto/adding-time-stamps-to-previously-signed-files).  
  
<a name="Verify"></a>

## <a name="verify-command-options"></a>"Verify"-Befehlsoptionen  
  
|"Verify"-Option|Beschreibung|  
|-------------------|-----------------|  
|`/a`|Gibt an, dass alle Methoden zum Überprüfen der Datei verwendet werden können. Zuerst werden die Katalogdatenbanken durchsucht, um zu ermitteln, ob die Datei in einem Katalog signiert ist. Wenn die Datei nicht in einem Katalog signiert ist, versucht das Signierungstool, die eingebettete Signatur der Datei zu überprüfen. Diese Option wird zum Überprüfen von Dateien empfohlen, die möglicherweise, jedoch nicht unbedingt in einem Katalog signiert sind. Beispiele für diese Dateien sind Windows-Dateien oder Treiber.|  
|`/ad`|Sucht den Katalog in der Standardkatalogdatenbank.|  
|`/ag` *CatDBGUID*|Sucht den Katalog in der durch *CatDBGUID* angegebenen Katalogdatenbank.|  
|`/all`|Überprüft alle Signaturen in einer Datei mit mehreren Signaturen.|  
|`/as`|Sucht den Katalog in der Katalogdatenbank der Systemkomponenten (Treiber).|  
|`/c` *CatFile*|Gibt die Katalogdatei anhand des Namens an.|  
|`/d`|Gibt an, dass die Beschreibung und Beschreibungs-URL vom Signierungstool gedruckt werden sollen.|  
|`/ds`  *Index*|Überprüft die Signatur an einer angegebenen Position.|  
|`/hash` (`SHA1`&#124;`SHA256`)|Gibt einen optionalen Hashalgorithmus zum Suchen einer Datei in einem Katalog an.|  
|`/kp`|Gibt an, dass die Überprüfung mit der Signierungsrichtlinie für Kernelmodustreiber ausgeführt werden soll.|  
|`/ms`|Verwendet mehrere Überprüfungssemantiken. Hierbei handelt es sich um das Standardverhalten eines [WinVerifyTrust](/windows/desktop/api/wintrust/nf-wintrust-winverifytrust)-Aufrufs unter Windows 8 und höher.|  
|`/o` *Version*|Überprüft die Datei anhand der Betriebssystemversion. *Version* hat das folgende Format: *PlatformID*:*VerMajor*.*VerMinor*.*BuildNumber*. *PlatformID* stellt den zugrundeliegenden Wert eines <xref:System.PlatformID>-Enumerationsmembers dar. **Wichtig:**  Die Verwendung des `/o`-Schalters wird empfohlen. Ohne Angabe von `/o` werden von SignTool.exe möglicherweise unerwartete Ergebnisse zurückgegeben. Beispiel: Wenn Sie den `/o`-Schalter nicht einbeziehen, werden unter älteren Betriebssystemen erfolgreich überprüfte Systemkataloge bei einem neueren Betriebssystem möglicherweise nicht ordnungsgemäß überprüft.|  
|`/p7`|Überprüft PKCS #7-Dateien. Bei der PKCS #7-Überprüfung werden keine vorhandenen Richtlinien verwendet. Die Signatur wird überprüft, und für das Signaturzertifikat wird eine Kette erstellt.|  
|`/pa`|Gibt an, dass die standardmäßige Authenticode-Überprüfungsrichtlinie verwendet werden soll. Ohne Angabe der `/pa`-Option wird vom Signierungstool die Windows-Treiberüberprüfungsrichtlinie verwendet. Diese Option kann nicht mit den `catdb`-Optionen verwendet werden.|  
|`/pg` *PolicyGUID*|Gibt eine Überprüfungsrichtlinie nach GUID an. Die *PolicyGUID* entspricht der „ActionID“ der Überprüfungsrichtlinie. Diese Option kann nicht mit den `catdb`-Optionen verwendet werden.|  
|`/ph`|Gibt an, dass Seitenhashwerte vom Signierungstool gedruckt und überprüft werden sollen.|  
|`/r` *RootSubjectName*|Gibt den Antragstellernamen des Stammzertifikats an, mit dem das Signaturzertifikat verkettet werden muss. Dieser Wert kann eine Teilzeichenfolge des gesamten Antragstellernamens des Stammzertifikats sein.|  
|`/tw`|Gibt an, dass bei einer Signatur ohne Zeitstempel eine Warnung generiert werden soll.|  
  
 Verwendungsbeispiele finden Sie unter [Using SignTool to Sign a File (Überprüfen einer Datei mit SignTool)](/windows/desktop/SecCrypto/using-signtool-to-verify-a-file-signature).  
  
## <a name="return-value"></a>Rückgabewert  

 Beim Beenden wird vom Signierungstool einer der folgenden Exitcodes zurückgegeben.  
  
|Exitcode|BESCHREIBUNG|  
|---------------|-----------------|  
|0|Ausführung war erfolgreich.|  
|1|Ausführung ist fehlgeschlagen.|  
|2|Ausführung wurde mit Warnungen abgeschlossen.|  

## <a name="examples"></a>Beispiele  

 Durch den folgenden Befehl wird der Systemkomponenten- und Treiberdatenbank die Katalogdatei "MyCatalogFileName.cat" hinzugefügt. Mit der `/u`-Option wird ggf. ein eindeutiger Name generiert, um das Ersetzen einer möglicherweise vorhandenen Katalogdatei mit dem Namen `MyCatalogFileName.cat` zu verhindern.  
  
```console  
signtool catdb /v /u MyCatalogFileName.cat  
```  
  
 Durch den folgenden Befehl wird eine Datei automatisch mit dem besten Zertifikat signiert.  
  
```console
signtool sign /a /fd SHA256 MyFile.exe
```

 Durch den folgenden Befehl wird eine Datei mit einem in einer kennwortgeschützten PFX-Datei gespeicherten Zertifikat digital signiert.  
  
```console  
signtool sign /f MyCert.pfx /p MyPassword /fd SHA256 MyFile.exe
```  
  
 Durch den folgenden Befehl wird eine Datei digital signiert und mit einem Zeitstempel versehen. Das zum Signieren der Datei verwendete Zertifikat ist in einer PFX-Datei gespeichert.  
  
```console  
signtool sign /f MyCert.pfx /t http://timestamp.digicert.com /fd SHA256 MyFile.exe
```  
  
 Durch den folgenden Befehl wird eine Datei mit einem Zertifikat aus dem `My`-Speicher signiert, das den Antragstellernamen `My Company Certificate` aufweist.  
  
```console  
signtool sign /n "My Company Certificate" /fd SHA256 MyFile.exe
```  
  
 Der folgende Befehl signiert ein ActiveX-Steuerelement und stellt Informationen bereit, die dem Benutzer in Internet Explorer bei der Aufforderung zum Installieren des Steuerelements angezeigt werden.  
  
```console  
Signtool sign /f MyCert.pfx /d: "MyControl" /du http://www.example.com/MyControl/info.html /fd SHA256 MyControl.exe
```  
  
 Durch den folgenden Befehl wird einer bereits digital signierten Datei ein Zeitstempel hinzugefügt.  
  
```console  
signtool timestamp /t http://timestamp.digicert.com MyFile.exe
```  

Der folgende Befehl versieht eine Datei unter Verwendung eines RFC 3161-Zeitstempelservers mit einem Zeitstempel.  
  
```console  
signtool timestamp /tr http://timestamp.digicert.com /td SHA256 MyFile.exe
```  
  
 Durch den folgenden Befehl wird überprüft, ob eine Datei signiert wurde.  
  
```console  
signtool verify MyFile.exe  
```  
  
 Durch den folgenden Befehl wird eine möglicherweise in einem Katalog signierte Systemdatei überprüft.  
  
```console  
signtool verify /a SystemFile.dll  
```  
  
 Durch den folgenden Befehl wird eine Systemdatei überprüft, die in einem Katalog mit dem Namen `MyCatalog.cat` signiert ist.  
  
```console  
signtool verify /c MyCatalog.cat SystemFile.dll  
```  
  
## <a name="see-also"></a>Siehe auch

- [Extras](index.md)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
