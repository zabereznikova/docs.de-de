---
title: Gacutil.exe (Global Assembly Cache-Tool)
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- global assembly cache, manipulating contents
- GAC (global assembly cache), Gacutil.exe
- Gacutil.exe
- GAC (global assembly cache), viewing contents
- installing assemblies into global assembly cache
- removing assemblies from global assembly cache
- list of assemblies in global assembly cache
- cache [.NET Framework], global assembly cache
- GAC (global assembly cache), manipulating contents
- global assembly cache, Gacutil.exe
- Global Assembly Cache tool
ms.assetid: 4c7be9c8-72ae-481f-a01c-1a4716806e99
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98423e6c103f7eb93b4bfa35ef19b6551c0df0e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399593"
---
# <a name="gacutilexe-global-assembly-cache-tool"></a>Gacutil.exe (Global Assembly Cache-Tool)
Das Global Assembly Cache-Tool ermöglicht das Anzeigen und Bearbeiten vom Inhalt des globalen Assemblycaches und des Downloadcaches.  
  
 Dieses Tool wird automatisch mit Visual Studio installiert. Zum Ausführen des Tools verwenden Sie die Developer-Eingabeaufforderung (oder die Visual Studio-Eingabeaufforderung in Windows 7). Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```  
gacutil [options] [assemblyName | assemblyPath | assemblyListFile]  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Argument|description|  
|--------------|-----------------|  
|*assemblyName*|Der Name einer Assembly. Sie können entweder einen teilweise angegebenen Assemblynamen, z. B. `myAssembly`, oder einen vollständig angegebenen Assemblynamen, z B. `myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5`, verwenden.|  
|*assemblyPath*|Der Name einer Datei, die ein Assemblymanifest enthält.|  
|*assemblyListFile*|Der Pfad zu einer ANSI-Textdatei, in der zu installierende oder zu deinstallierende Assemblys aufgeführt sind. Wenn Sie zum Installieren von Assemblys eine Textdatei verwenden möchten, geben Sie den Pfad zu den einzelnen Assemblys in der Datei jeweils in eigenen Zeilen an. Das Tool interpretiert relative Pfade als relativ zum Speicherort von *assemblyListFile*. Wenn Sie zum Deinstallieren von Assemblys eine Textdatei verwenden möchten, geben Sie den vollqualifizierten Namen der einzelnen Assemblys jeweils in eigenen Zeilen in der Datei an. Weitere Informationen hierzu finden Sie in den Beispielen zum Inhalt von *assemblyListFile* weiter unten in diesem Thema.|  
  
|Option|description|  
|------------|-----------------|  
|**/cdl**|Löscht den Inhalt des Downloadcaches.|  
|**/f**|Geben Sie zum Erzwingen der Neuinstallation einer Assembly diese Option mit der **/i**-Option oder der **/il**-Option an. Wenn im globalen Assemblycache bereits eine Assembly mit demselben Namen vorhanden ist, wird diese vom Tool überschrieben.|  
|**-h**[**elp**]|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|**/i** *assemblyPath*|Installiert eine Assembly in den globalen Assemblycache.|  
|**/if**  *assemblyPath*|Installiert eine Assembly in den globalen Assemblycache. Wenn im globalen Assemblycache bereits eine Assembly mit demselben Namen vorhanden ist, wird diese vom Tool überschrieben.<br /><br /> Die Angabe dieser Option entspricht der kombinierten Angabe der **/i**-Option und der **/f**-Option.|  
|**/il** *assemblyListFile*|Installiert eine oder mehrere in *assemblyListFile* angegebene Assemblys im globalen Assemblycache.|  
|**/ir**  *assemblyPath*<br /><br /> *Schema*<br /><br /> *ID*<br /><br /> *Beschreibung*|Installiert eine Assembly im globalen Assemblycache und fügt einen Verweis zum Zählen der Assembly hinzu. Die Parameter *assemblyPath*, *scheme*, *id* und *description* müssen mit dieser Option angegeben werden. Eine Beschreibung der gültigen Werte, die für diese Parameter angegeben werden können, finden Sie unter der **/r**-Option.<br /><br /> Die Angabe dieser Option entspricht der kombinierten Angabe der **/i**-Option und der **/r**-Option.|  
|**/l** [*assemblyName*]|Listet den Inhalt des globalen Assemblycaches auf. Wenn Sie den *assemblyName*-Parameter angeben, werden vom Tool nur die mit diesem Namen übereinstimmenden Assemblys aufgelistet.|  
|**/ldl**|Listet den Cacheinhalt der heruntergeladenen Dateien auf.|  
|**/lr** [*assemblyName*]|Listet alle Assemblys und die entsprechenden Verweiszähler auf. Bei Angabe des *assemblyName*-Parameters werden vom Tool nur die mit diesem Namen übereinstimmenden Assemblys sowie die entsprechenden Verweiszähler aufgelistet.|  
|**/nologo**|Unterdrückt die Anzeige des Startbanners von Microsoft.|  
|**/r** [*assemblyName &#124; assemblyPath*]<br /><br /> *Schema*<br /><br /> *ID*<br /><br /> *Beschreibung*|Gibt einen zurückverfolgten Verweis auf Assemblys an, die installiert oder deinstalliert werden sollen. Geben Sie diese Option mit den Optionen **/i**, **/il**, **/u** oder **/ul** an.<br /><br /> Um eine Assembly zu installieren, müssen Sie die Parameter *assemblyPath*, *scheme*, *id* und *description* mit dieser Option angeben. Geben Sie zum Deinstallieren einer Assembly die Parameter *assemblyName*, *scheme*, *id* und *description* an.<br /><br /> Um einen Verweis auf eine Assembly zu entfernen, müssen Sie dieselben Parameter *scheme*, *id* und *description* angeben, die beim Installieren der Assembly mit der **/i**-Option und der **/r**-Option (bzw. der **/ir**-Option) angegeben wurden. Bei der Deinstallation einer Assembly wird die Assembly vom Tool auch aus dem globalen Assemblycache entfernt, sofern es sich um den letzten zu entfernenden Verweis handelt und der Windows Installer keine ausstehenden Verweise auf die Assembly findet.<br /><br /> Mit dem *scheme*-Parameter wird der Typ des Installationsschemas angegeben. Sie können einen der folgenden Werte angeben:<br /><br /> – UNINSTALL_KEY: Geben Sie diesen Wert an, wenn das Installationsprogramm die Anwendung in Microsoft Windows unter „Software“ hinzufügt. Anwendungen werden unter "Software" automatisch hinzugefügt, indem unter HKLM\Software\Microsoft\Windows\CurrentVersion ein Registrierungsschlüssel hinzugefügt wird.<br />– FILEPATH: Geben Sie diesen Wert an, wenn die Anwendung durch das Installationsprogramm nicht unter „Software“ hinzugefügt wird.<br />– OPAQUE: Geben Sie diesen Wert an, wenn bei der Installation kein Registrierungsschlüssel oder Dateipfad angegeben werden kann. Mithilfe dieses Werts können Sie benutzerdefinierte Informationen für den *id*-Parameter angeben.<br /><br /> Der für den *id*-Parameter anzugebende Wert hängt von dem für den *scheme*-Parameter angegeben Wert ab:<br /><br /> Wenn Sie für den *scheme*-Parameter UNINSTALL_KEY angeben, geben Sie den im Registrierungsschlüssel HKLM\Software\Microsoft\Windows\CurrentVersion festgelegten Namen der Anwendung an. Lautet der Registrierungsschlüssel z.B. HKLM\Software\Microsoft\Windows\CurrentVersion\MyApp, geben Sie als *id*-Parameter „MyApp“ an.<br />– Wenn Sie als *scheme*-Parameter „FILEPATH“ angeben, geben Sie den vollständigen Pfad der ausführbaren Datei an, mit der die Assembly als *id*-Parameter installiert wird.<br />Wenn Sie als *scheme*-Parameter „OPAQUE“ angeben, können Sie beliebige Daten als *id*-Parameter angeben. Die angegebenen Daten müssen in Anführungszeichen ("") eingeschlossen sein.<br /><br /> Mithilfe des *description*-Parameters können Sie einen beschreibenden Text für die zu installierende Anwendung eingeben. Diese Informationen werden beim Auflisten von Verweisen angezeigt.|  
|**/silent**|Die Anzeige aller Datenausgaben werden unterdrückt.|  
|**/u**  *assemblyName*|Deinstalliert eine Assembly aus dem globalen Assemblycache.|  
|**/uf**  *assemblyName*|Erzwingt die Deinstallation einer angegebenen Assembly durch Entfernen aller Verweise auf die Assembly.<br /><br /> Die Angabe dieser Option entspricht der kombinierten Angabe der **/u**-Option und der **/f**-Option. **Hinweis:** Mit dieser Option können Sie keine Assembly entfernen, die mit dem Microsoft Windows Installer installiert wurde. Bei einem Versuch, diesen Vorgang auszuführen, wird vom Tool eine Fehlermeldung angezeigt.|  
|**/ul** *assemblyListFile*|Mindestens eine in *assemblyListFile* angegebene Assembly wird aus dem globalen Assemblycache deinstalliert.|  
|**/u**[**ngen**] *assemblyName*|Eine bestimmte Assembly wird aus dem globalen Assemblycache deinstalliert. Wenn die angegebene Assembly über einen Zähler für vorhandene Verweise verfügt, wird der Verweiszähler vom Tool angezeigt, und die Assembly wird nicht aus dem globalen Assemblycache entfernt. **Hinweis:** In der .NET Framework-Version 2.0 wird `/ungen` nicht unterstützt. Verwenden Sie stattdessen den `uninstall`-Befehl von [Ngen.exe (Native Image Generator)](../../../docs/framework/tools/ngen-exe-native-image-generator.md). <br /><br /> In .NET Framework, Version 1.0 und 1.1 wird bei Angabe von **/ungen** die Assembly von „Gacutil.exe“ aus dem nativen Imagecache entfernt. In diesem Cache werden die nativen Images für Assemblys gespeichert, die mit dem [Ngen.exe (Native Image Generator)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) erstellt wurden.|  
|**/ur**  *assemblyName*<br /><br /> *Schema*<br /><br /> *ID*<br /><br /> *Beschreibung*|Deinstalliert einen Verweis auf eine angegebene Assembly aus dem globalen Assemblycache. Um einen Verweis auf eine Assembly zu entfernen, müssen Sie dieselben Parameter *scheme*, *id* und *description* angeben, die beim Installieren der Assembly mit der **/i**-Option und der **/r**-Option (bzw. der **/ir**-Option) angegeben wurden. Eine Beschreibung der gültigen Werte, die für diese Parameter angegeben werden können, finden Sie unter der **/r**-Option.<br /><br /> Die Angabe dieser Option entspricht der kombinierten Angabe der **/u**-Option und der **/r**-Option.|  
|**/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Sie müssen zum Verwenden von "Gacutil.exe" über Administratorrechte verfügen.  
  
 "Gacutil.exe" ermöglicht Ihnen insbesondere das Installieren von Assemblys im Cache, das Entfernen von Assemblys aus dem Cache sowie das Auflisten des Cacheinhalts.  
  
 "Gacutil.exe" bietet Optionen zur Unterstützung einer Verweiszählung, die dem von Windows Installer unterstützten Verweiszählungsschema ähnelt. Mit "Gacutil.exe" können Sie zwei Anwendungen installieren, die dieselbe Assembly installieren. Dabei wird die Anzahl von Verweisen auf die Assembly vom Tool verfolgt. Daher verbleibt die Assembly auf dem Computer, bis beide Anwendungen deinstalliert wurden. Wenn Sie "Gacutil.exe" für die eigentliche Produktinstallation einsetzen, nutzen Sie die Optionen, mit denen die Verweiszählung unterstützt wird. Bei gleichzeitiger Verwendung der **/i**-Option und der **/r**-Option können Sie eine Assembly installieren und einen Verweis für die Zählung hinzufügen. Bei gleichzeitiger Verwendung der **/u**-Option und der **/r**-Option können Sie einen Verweiszähler für eine Assembly entfernen. Beachten Sie, dass weder die **/i**-Option noch die **/u**-Option allein die Verweiszählung unterstützt. Diese Optionen sind für die Verwendung während der Produktentwicklung geeignet, jedoch nicht für die eigentliche Produktinstallation.  
  
 Mit der **/il**-Option oder der **/ul**-Option können Sie eine Liste von Assemblys installieren bzw. deinstallieren, die in einer ANSI-Textdatei gespeichert ist. Der Inhalt der Textdatei muss korrekt formatiert sein. Wenn Sie zum Installieren von Assemblys eine Textdatei verwenden möchten, geben Sie den Pfad zu den einzelnen Assemblys in der Datei jeweils in eigenen Zeilen an. Im folgenden Beispiel wird der Inhalt einer Datei veranschaulicht, in der zu installierende Assemblys enthalten sind.  
  
```  
myAssembly1.dll  
myAssembly2.dll  
myAssembly3.dll  
```  
  
 Wenn Sie zum Deinstallieren von Assemblys eine Textdatei verwenden möchten, geben Sie den vollqualifizierten Namen der einzelnen Assemblys jeweils in eigenen Zeilen in der Datei an. Im folgenden Beispiel wird der Inhalt einer Datei veranschaulicht, in der zu deinstallierende Assemblys enthalten sind.  
  
```  
myAssembly1,Version=1.1.0.0,Culture=en,PublicKeyToken=874e23ab874e23ab  
myAssembly2,Version=1.1.0.0,Culture=en,PublicKeyToken=874e23ab874e23ab  
myAssembly3,Version=1.1.0.0,Culture=en,PublicKeyToken=874e23ab874e23ab  
```  
  
## <a name="examples"></a>Beispiele  
 Mit dem folgenden Befehl wird die Assembly `mydll.dll` im globalen Assemblycache installiert.  
  
```  
gacutil /i mydll.dll  
```  
  
 Mit dem folgenden Befehl wird die Assembly `hello` aus dem globalen Assemblycache entfernt, sofern für die Assembly keine Verweiszählung vorhanden ist.  
  
```  
gacutil /u hello  
```  
  
 Mit dem vorherigen Befehl können mehrere Assemblys aus dem Assemblycache entfernt werden, da der Assemblyname nicht vollständig angegeben ist. Wenn z. B. Version 1.0.0.0 und Version 3.2.2.1 von `hello` im Cache installiert sind, werden mit dem Befehl `gacutil /u hello` beide Assemblys entfernt.  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie das Entfernen mehrerer Assemblys vermeiden. Mit diesem Befehl wird lediglich die Assembly `hello` entfernt, die der vollständig angegebenen Versionsnummer, der Kultur und dem öffentlichen Schlüssel entspricht.  
  
```  
gacutil /u hello, Version=1.0.0.1, Culture="de",PublicKeyToken=45e343aae32233ca  
```  
  
 Mit dem folgenden Befehl werden die in der Datei `assemblyList.txt` angegebenen Assemblys im globalen Assemblycache installiert.  
  
 `gacutil /il assemblyList.txt`  
  
 Mit dem folgenden Befehl werden die in der Datei `assemblyList.txt` angegebenen Assemblys aus dem globalen Assemblycache entfernt.  
  
 `gacutil /ul assemblyList.txt`  
  
 Mit dem folgenden Befehl wird `myDll.dll` im globalen Assemblycache installiert, und es wird ein Verweis für die Zählung hinzugefügt. Die Assembly `myDll.dll` wird von der Anwendung `MyApp` verwendet. Mit dem `UNINSTALL_KEY MyApp` -Parameter wird der Registrierungsschlüssel angegeben, mit dem `MyApp` in Windows der Liste unter "Software" hinzufügt wird. Der description-Parameter wird als `My Application Description` angegeben.  
  
```  
gacutil /i /r myDll.dll UNINSTALL_KEY MyApp "My Application Description"  
```  
  
 Mit dem folgenden Befehl wird `myDll.dll` im globalen Assemblycache installiert, und es wird ein Verweis für die Zählung hinzugefügt. Der scheme-Parameter `FILEPATH` und der id-Parameter `c:\applications\myApp\myApp.exe` geben den Pfad der Anwendung an, von der die `myDll.dll.` installiert wird. Der description-Parameter wird als `MyApp` angegeben.  
  
 `gacutil /i /r myDll.dll FILEPATH c:\applications\myApp\myApp.exe MyApp`  
  
 Mit dem folgenden Befehl wird `myDll.dll` im globalen Assemblycache installiert, und es wird ein Verweis für die Zählung hinzugefügt. Der scheme-Parameter `OPAQUE` ermöglicht die Anpassung des id-Parameters und des description-Parameters.  
  
```  
gacutil /i /r mydll.dll OPAQUE "Insert custom application details here" "Insert Custom description information here"  
```  
  
 Mit dem folgenden Befehl wird der Verweis auf `myDll.dll` von der Anwendung `myApp` entfernt. Wenn es sich hierbei um den letzten Verweis auf die Assembly handelt, wird auch die Assembly aus dem Assemblycache entfernt.  
  
 `gacutil /u /r myDll.dll FILEPATH c:\applications\myApp\myApp.exe MyApp`  
  
 Der folgende Befehl listet den Inhalt des globalen Assemblycaches auf.  
  
```  
gacutil /l  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Extras](../../../docs/framework/tools/index.md)  
 [Globaler Assemblycache](../../../docs/framework/app-domains/gac.md)  
 [Regasm.exe (Assembly Registration-Tool)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)  
 [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
