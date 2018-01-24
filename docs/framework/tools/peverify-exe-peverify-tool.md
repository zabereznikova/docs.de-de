---
title: Peverify.exe (PEVerify-Tool)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- portable executable files, PEVerify
- verifying MSIL and metadata
- PEVerify tool
- type safety requirements
- MSIL
- PEverify.exe
- PE files, PEVerify
ms.assetid: f4f46f9e-8d08-4e66-a94b-0c69c9b0bbfa
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5acb6da7c68f899daa4144e897e9ec31fcfa868a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="peverifyexe-peverify-tool"></a>Peverify.exe (PEVerify-Tool)
Mit dem PEVerify-Tool können Entwickler, die MSIL (Microsoft Intermediate Language) generieren (Compilerentwickler, Skriptmodulentwickler usw.), herausfinden, ob ihr MSIL-Code und die zugeordneten Metadaten den Anforderungen an die Typsicherheit entsprechen. Einige Compiler generieren nur dann überprüfbar typsicheren Code, wenn bestimmte Sprachkonstrukte nicht verwendet werden. Wenn Sie als Entwickler einen solchen Compiler verwenden, sollten Sie unter Umständen prüfen, ob die Typsicherheit des Codes eingeschränkt wurde. Hierzu können Sie das PEVerify-Tool für die Dateien ausführen und damit die MSIL und Metadaten überprüfen.  
  
 Dieses Tool wird automatisch mit Visual Studio installiert. Zum Ausführen des Tools verwenden Sie die Developer-Eingabeaufforderung (oder die Visual Studio-Eingabeaufforderung in Windows 7). Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```  
peverify filename [options]  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Argument|description|  
|--------------|-----------------|  
|*filename*|Die portierbare ausführbare Datei (Portable Executable, PE), deren MSIL und Metadaten überprüft werden sollen.|  
  
|Option|description|  
|------------|-----------------|  
|**/break=** *maxErrorCount*|Bricht die Überprüfung nach *maxErrorCount*-Fehlern ab.<br /><br /> Dieser Parameter wird in .NET Framework, Version 2.0 oder höher, nicht unterstützt.|  
|**/clock**|Erfasst und meldet die folgenden Überprüfungszeiten in Millisekunden:<br /><br /> **MD Val. cycle**<br /> Validierungszyklus der Metadaten<br /><br /> **MD Val. pure**<br /> Reine Metadatenvalidierung<br /><br /> **IL Ver. cycle**<br /> Überprüfungszyklus der Microsoft Intermediate Language (MSIL)<br /><br /> **IL Ver pure**<br /> Reine MSIL-Überprüfung<br /><br /> Die Zeiten **MD Val. cycle** und **IL Ver. cycle** umfassen die Zeit, die erforderlich ist, um die notwendigen Prozeduren zum Starten und Herunterfahren auszuführen. Die Zeiten **MD Val. pure** und **IL Ver pure** umfassen die Zeit, die erforderlich ist, um nur die Validierung oder Überprüfung auszuführen.|  
|**/help**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|**/hresult**|Zeigt Fehlercodes im Hexadezimalformat an.|  
|**/ignore=** *hex.code* [, *hex.code*]|Ignoriert die angegebenen Fehlercodes.|  
|**/ignore=@** *antwortdatei*|Ignoriert die in der angegebenen Antwortdatei aufgelisteten Fehlercodes.|  
|**/il**|Führt Überprüfungen der MSIL-Typsicherheit für Methoden durch, die in der durch *dateiname* angegebenen Assembly implementiert sind. Das Tool gibt eine detaillierte Beschreibung aller gefundenen Probleme zurück, sofern Sie nicht die **/quiet**-Option angeben.|  
|**/md**|Führt Validierungen von Metadaten in der durch *Dateiname* angegebenen Assembly aus. Dabei wird die gesamte Metadatenstruktur in der Datei durchlaufen und über alle gefundenen Validierungsprobleme berichtet.|  
|**/nologo**|Unterdrückt die Anzeige der Produktversion sowie von Copyrightinformationen.|  
|**/nosymbols**|Unterdrückt in .NET Framework, Version 2.0, Zeilennummern, um Abwärtskompatibilität zu gewährleisten.|  
|**/quiet**|Gibt den stillen Modus an. Hierbei wird die Ausgabe von Berichten über die während der Überprüfung gefundenen Probleme unterdrückt. "Peverify.exe" meldet weiterhin, ob die Datei typsicher ist, es werden jedoch keine Informationen zu Problemen ausgegeben, die die Überprüfung der Typsicherheit verhindern.|  
|`/transparent`|Überprüfen Sie nur die transparenten Methoden.|  
|**/unique**|Ignoriert wiederholt auftretende Fehlercodes.|  
|**/verbose**|Zeigt in .NET Framework, Version 2.0, zusätzliche Informationen in MSIL-Überprüfungsmeldungen an.|  
|**/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Common Language Runtime erfordert die typsichere Ausführung von Anwendungscode, um Sicherheits- und Isolierungsmechanismen zu erzwingen. Normalerweise kann Code, der nicht [überprüfbar typsicher](http://msdn.microsoft.com/library/095cd1f6-d8db-4c0e-bce2-83ccb34dd5dc) ist, nicht ausgeführt werden. Sie können jedoch die Sicherheitsrichtlinie so festlegen, dass vertrauenswürdiger, aber nicht überprüfbarer Code ausgeführt wird.  
  
 Wenn weder die **/md**-Option noch die **/il**-Option angegeben wurde, führt „peverify.exe“ beide Überprüfungen durch. „everify.exe“ führt zuerst **/md**-Überprüfungen aus. Wenn keine Fehler auftreten, werden **/il**-Überprüfungen durchgeführt. Wenn Sie **/md** und **/il** angeben, werden auch **/il**-Überprüfungen durchgeführt, wenn in den Metadaten Fehler vorhanden sind. Daher stimmt **peverify** *dateiname* mit **peverify** *dateiname* **/md** **/il** überein, wenn die Metadaten nicht fehlerhaft sind.  
  
 "Peverify.exe" führt umfangreiche MSIL-Überprüfungen anhand der Datenflussanalyse sowie einer Liste mit mehreren hundert Regeln für die Gültigkeit von Metadaten durch. Detaillierte Informationen zu den von "Peverify.exe" ausgeführten Überprüfungen finden Sie im [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] im Ordner "Tools Developers Guide" unter "Metadata Validation Specification" und "MSIL Instruction Set Specification".  
  
 Beachten Sie, dass .NET Framework, Version 2.0 oder höher, überprüfbare `byref`-Rückgaben unterstützt, die unter Verwendung der folgenden MSIL-Anweisungen angegeben werden: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call` und `unbox`.  
  
## <a name="examples"></a>Beispiele  
 Der folgende Befehl validiert Metadaten und verifiziert die MSIL-Typsicherheit von Methoden, die in der `myAssembly.exe`-Assembly implementiert sind.  
  
```  
peverify myAssembly.exe /md /il  
```  
  
 Wenn diese Anforderung erfolgreich ausgeführt wurde, zeigt "Peverify.exe" die folgende Meldung an.  
  
```  
All classes and methods in myAssembly.exe Verified  
```  
  
 Der folgende Befehl validiert Metadaten und verifiziert die MSIL-Typsicherheit von Methoden, die in der `myAssembly.exe`-Assembly implementiert sind. Das Tool zeigt an, wie viel Zeit zur Durchführung dieser Überprüfungen erforderlich ist.  
  
```  
peverify myAssembly.exe /md /il /clock  
```  
  
 Wenn diese Anforderung erfolgreich ausgeführt wurde, zeigt "Peverify.exe" die folgende Meldung an.  
  
```  
All classes and methods in myAssembly.exe Verified  
Timing: Total run     320 msec  
        MD Val.cycle  40 msec  
        MD Val.pure   10 msec  
        IL Ver.cycle  270 msec  
        IL Ver.pure   230 msec  
```  
  
 Der folgende Befehl validiert Metadaten und verifiziert die MSIL-Typsicherheit von Methoden, die in der `myAssembly.exe`-Assembly implementiert sind. "Peverify.exe" wird jedoch beendet, wenn es die maximale Fehleranzahl von 100 erreicht. Das Tool ignoriert auch die angegebenen Fehlercodes.  
  
```  
peverify myAssembly.exe /break=100 /ignore=0x12345678,0xABCD1234  
```  
  
 Der folgende Befehl führt zum gleichen Ergebnis wie das vorherige Beispiel, nur werden hier die in der Antwortdatei `ignoreErrors.rsp` zu ignorierenden Fehlercodes angegeben.  
  
```  
peverify myAssembly.exe /break=100 /ignore@ignoreErrors.rsp  
```  
  
 Die Antwortdatei kann eine durch Trennzeichen getrennte Liste von Fehlercodes enthalten.  
  
```  
0x12345678, 0xABCD1234  
```  
  
 Wahlweise kann die Antwortdatei auch mit einem Fehlercode pro Zeile formatiert werden.  
  
```  
0x12345678  
0xABCD1234  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Extras](../../../docs/framework/tools/index.md)  
 [NIB: Schreiben von überprüfbar typsicherem Code](http://msdn.microsoft.com/library/d18f10ef-3b48-4f47-8726-96714021547b)  
 [Typsicherheit und Sicherheit](http://msdn.microsoft.com/library/095cd1f6-d8db-4c0e-bce2-83ccb34dd5dc)  
 [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
