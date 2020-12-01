---
title: Certmgr.exe (Certificate Manager-Tool)
description: Untersuchen von Certmgr.exe, dem Certificate Manager-Tool. Dieses Tool verwaltet Zertifikate, CTLs (Certificate Trust Lists, Zertifikatsvertrauenslisten) und CRLs (Certificate Revocation Lists, Zertifikatssperrlisten).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates, managing
- CRLs
- certificate trust lists
- Certmgr.exe
- Certificate Manager tool
- CTLs
- certificate revocation lists
ms.assetid: 7e953b43-1374-4bbc-814f-53ca1b6b52bb
ms.openlocfilehash: 30a35ded6fc86af6dc6dd4bf19cdf60f66570e0c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247251"
---
# <a name="certmgrexe-certificate-manager-tool"></a>Certmgr.exe (Certificate Manager-Tool)

Mit dem Certificate Manager-Tool (Certmgr.exe) können Sie Zertifikate, Zertifikatvertrauenslisten (Certificate Trust Lists, CTLs) und Zertifikatsperrlisten (Certificate Revocation Lists, CRLs) verwalten.  
  
 Das Certificate Manager-Tool wird automatisch mit Visual Studio installiert. Verwenden Sie zum Starten des Tools die [Eingabeaufforderungen](developer-command-prompt-for-vs.md).  
  
> [!NOTE]
> Das Certificate Manager-Tool (Certmgr.exe) ist ein Befehlszeilendienstprogramm, wohingegen "Zertifikate" (Certmgr.msc) ein MMC-Snap-In (Microsoft Management Console) ist. Da sich „Certmgr.msc“ normalerweise im Windows-Systemverzeichnis befindet, kann durch die Eingabe von `certmgr` in der Befehlszeile das MMC-Snap-In „Zertifikate“ geladen werden, auch wenn Sie die Developer-Eingabeaufforderung für Visual Studio geöffnet haben. Dies geschieht, weil der Pfad zum Snap-In dem Pfad für das Certificate Manager-Tool in der PATH-Umgebungsvariablen vorangestellt ist. Wenn dieses Problem auftritt, können Sie "Certmgr.exe"-Befehle ausführen, indem Sie den Pfad zu der ausführbaren Datei angeben.  
  
 Dieses Tool wird automatisch mit Visual Studio installiert. Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).  
  
 Einen Überblick über X.509-Zertifikate finden Sie unter [Arbeiten mit Zertifikaten](../wcf/feature-details/working-with-certificates.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```console  
      certmgr [/add | /del | /put] [options]  
[/s[/r registryLocation]] [sourceStorename]  
[/s[/r registryLocation]] [destinationStorename]  
```  
  
## <a name="parameters"></a>Parameter  
  
|Argument|BESCHREIBUNG|  
|--------------|-----------------|  
|*sourceStorename*|Der Zertifikatspeicher, der die vorhandenen Zertifikate, die CTLs oder CRLs enthält, die hinzugefügt, gelöscht, gespeichert oder angezeigt werden sollen. Dabei kann es sich um eine Speicherdatei oder einen Systemspeicher handeln.|  
|*destinationStorename*|Der Ausgabezertifikatsspeicher bzw. die Ausgabedatei.|  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/add**|Fügt einem Zertifikatsspeicher Zertifikate, CTLs und CRLs hinzu.|  
|**/all**|Fügt bei der Verwendung mit **/add** alle Einträge hinzu. Löscht bei der Verwendung mit **/del** alle Einträge. Zeigt bei der Verwendung ohne die Option **/add** oder **/del** alle Einträge an. Die Option **/all** kann nicht mit **/put** verwendet werden.|  
|**/c**|Fügt bei der Verwendung mit **/add** Zertifikate hinzu. Löscht Zertifikate bei der Verwendung mit **/del**. Speichert Zertifikate bei der Verwendung mit **/put**. Zeigt bei der Verwendung ohne die Optionen **/add**, **/del** und **/put** Zertifikate an.|  
|**/CRL**|Fügt bei der Verwendung mit **/add** CRLs hinzu. Löscht CRLs bei der Verwendung mit **/del**. Speichert CRLs bei der Verwendung mit **/put**. Zeigt bei der Verwendung ohne die Optionen **/add**, **/del** und **/put** CRLs an.|  
|**/CTL**|Fügt bei der Verwendung mit **/add** CTLs hinzu. Löscht CTLs bei der Verwendung mit **/del**. Speichert CTLs bei der Verwendung mit **/put**. Zeigt bei der Verwendung ohne die Option **/add**, **/del** oder **/put** CTLs an.|  
|**/del**|Löscht Zertifikate, CTLs und CRLs aus einem Zertifikatspeicher.|  
|**/e** *encodingType*|Gibt den Codierungstyp des Zertifikats an. Der Standardwert ist `X509_ASN_ENCODING`.|  
|**/f** *dwFlags*|Gibt das Flag zum Öffnen des Speichers an. Dies ist der an *CertOpenStore* übergebene Parameter **dwFlags**. Der Standardwert ist CERT_SYSTEM_STORE_CURRENT_USER. Diese Option wird nur bei der Verwendung der Option **/y** berücksichtigt.|  
|**/h**[**elp**]|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|**/n** *nam*|Gibt den allgemeinen Namen des Zertifikats an, das hinzugefügt, gelöscht oder gespeichert werden soll. Diese Option kann nur für Zertifikate und nicht für CTLs und CRLs verwendet werden.|  
|**/put**|Speichert ein X.509-Zertifikat, eine CTL oder eine CRL aus einem Zertifikatspeicher in einer Datei. Die Datei wird im Format X.509 gespeichert. Sie können die Option **/7** zusammen mit der Option **/put** verwenden, um die Datei im PKCS #7-Format zu speichern. Auf die Option **/put** muss entweder **/c**, **/CTL** oder **/CR** folgen. Die Option **/all** kann nicht mit **/put** verwendet werden.|  
|**/r** *location*|Gibt den Speicherort des Systemspeichers in der Registrierung an. Diese Option wird nur berücksichtigt, wenn Sie die Option **/s** angeben. Für *location* muss einer der folgenden Werte angegeben werden:<br /><br /> -   `currentUser` gibt an, dass sich der Zertifikatspeicher unter dem Schlüssel HKEY_CURRENT_USER befindet. Dies ist die Standardeinstellung.<br />-   `localMachine` gibt an, dass sich der Zertifikatspeicher unter dem Schlüssel HKEY_LOCAL_MACHINE befindet.|  
|**/s**|Gibt an, dass der Zertifikatspeicher ein Systemspeicher ist. Wenn Sie diese Option nicht angeben, wird angenommen, dass der Speicher vom Typ **StoreFile** ist.|  
|**/sha1** *sha1Hash*|Gibt den SHA1-Hash des Zertifikats, der CTL oder der CRL an, das bzw. die hinzugefügt, gelöscht oder gespeichert werden soll.|  
|**/v**|Gibt den ausführlichen Modus an und zeigt detaillierte Informationen über Zertifikate, CTLs und CRLs an. Diese Option kann nicht mit den Optionen **/add**, **/del** und **/put** verwendet werden.|  
|**/y** *provider*|Gibt den Namen des Speicheranbieters an.|  
|**/7**|Speichert den Zielspeicher als PKCS #7-Objekt.|  
|**/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
## <a name="remarks"></a>Hinweise  

 Von "Certmgr.exe" werden die folgenden Basisfunktionen ausgeführt:  
  
- Zeigt Zertifikate, CTLs und CRLs in der Konsole an.  
  
- Fügt einem Zertifikatsspeicher Zertifikate, CTLs und CRLs hinzu.  
  
- Löscht Zertifikate, CTLs und CRLs aus einem Zertifikatspeicher.  
  
- Speichert ein X.509-Zertifikat, eine CTL oder eine CRL aus einem Zertifikatspeicher in einer Datei.  
  
 In „Certmgr.exe“ werden zwei Typen von Zertifikatspeichern verwendet: **StoreFile** und der Systemspeicher. Sie müssen den Typ des Zertifikatspeichers nicht angeben. "Certmgr.exe" kann den Speichertyp erkennen und die entsprechenden Operationen ausführen.  
  
 Wird "Certmgr.exe" ohne Angabe von Optionen ausgeführt, wird das Snap-In "Certmgr.msc" gestartet. Dessen grafische Benutzeroberfläche (GUI) erleichtert die Aufgaben der Zertifikatsverwaltung, die auch über die Befehlszeile zur Verfügung stehen. Die grafische Benutzeroberfläche bietet einen Import-Assistenten, der Zertifikate, CTLs und CRLs vom Datenträger in einen Zertifikatspeicher kopiert.  
  
 Sie können die Namen von "X509Certificate"-Speichern für die Parameter `sourceStorename` und `destinationStorename` suchen, indem Sie den folgenden Code kompilieren und ausführen.  
  
 [!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)]
 [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]  
  
 Weitere Informationen zu Zertifikaten finden Sie unter [Arbeiten mit Zertifikaten](../wcf/feature-details/working-with-certificates.md).  
  
## <a name="examples"></a>Beispiele  

 Mit dem folgenden Befehl wird der Standardsystemspeicher `my` mit ausführlicher Ausgabe angezeigt.  
  
```console  
certmgr /v /s my  
```  
  
 Mit dem folgenden Befehl werden alle Zertifikate in der Datei `myFile.ext` einer neuen Datei mit dem Namen `newFile.ext` hinzugefügt.  
  
```console  
certmgr /add /all /c myFile.ext newFile.ext  
```  
  
 Mit dem folgenden Befehl wird das Zertifikat in der Datei `testcert.cer` zum Systemspeicher `my` hinzugefügt.  
  
```console  
certmgr /add /c testcert.cer /s my  
```  
  
 Mit dem folgenden Befehl wird das Zertifikat in der Datei `TrustedCert.cer` zum Stammzertifikatsspeicher hinzugefügt.  
  
```console  
certmgr /c /add TrustedCert.cer /s root  
```  
  
 Mit dem folgenden Befehl wird ein Zertifikat mit dem allgemeinen Namen `myCert` im Systemspeicher `my` in die Datei `newCert.cer` gespeichert.  
  
```console  
certmgr /add /c /n myCert /s my newCert.cer  
```  
  
 Mit dem folgenden Befehl werden alle CTLs im Systemspeicher `my` gelöscht. Der sich ergebende Speicher wird anschließend in der Datei `newStore.str` gespeichert.  
  
```console  
certmgr /del /all /ctl /s my newStore.str  
```  
  
 Mit dem folgenden Befehl wird ein Zertifikat im Systemspeicher `my` in der Datei `newFile` gespeichert. Sie werden aufgefordert, die Nummer des Zertifikats aus `my` einzugeben, das in `newFile` abgelegt werden soll.  
  
```console  
certmgr /put /c /s my newFile  
```  
  
## <a name="see-also"></a>Siehe auch

- [Extras](index.md)
- [Makecert.exe (Tool für die Zertifikaterstellung)](/windows/desktop/SecCrypto/makecert)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
