---
title: Regsvcs.exe (.NET Services Installation-Tool)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ddd937ec891f5e00410b74fffd152e23431652f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="regsvcsexe-net-services-installation-tool"></a>Regsvcs.exe (.NET Services Installation-Tool)
Mit dem .NET Services Installation-Tool können folgende Aktionen ausgeführt werden:  
  
-   Laden und Registrieren einer Assembly  
  
-   Generieren, Registrieren und Installieren einer Typbibliothek in einer angegebenen COM+-Anwendung  
  
-   Konfigurieren von Diensten, die Sie programmgesteuert einer Klasse hinzugefügt haben  
  
 Zum Ausführen des Tools verwenden Sie die Developer-Eingabeaufforderung (oder die Visual Studio-Eingabeaufforderung in Windows 7). Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll   
```  
  
#### <a name="parameters"></a>Parameter  
  
|Argument|Beschreibung|  
|--------------|-----------------|  
|*assemblyFile.dll*|Die Quelldatei für die Assembly. Die Assembly muss mit einem starken Namen signiert sein. Weitere Informationen dazu finden Sie unter [Signing an Assembly with a Strong Name (Signieren einer Assembly mit starkem Namen)](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).|  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**/appdir:** *pfad*|Gibt das Stammverzeichnis der Anwendung an.|  
|**/appname:** *anwendungsname*|Gibt den Namen der zu suchenden oder zu erstellenden COM+-Anwendung an.|  
|**/c**|Erstellt die Zielanwendung.|  
|**/componly**|Konfiguriert nur Komponenten und ignoriert Methoden und Schnittstellen.|  
|**/exapp**|Legt für das Tool fest, dass eine vorhandene Anwendung erwartet wird.|  
|**/extlb**|Verwendet eine vorhandene Typbibliothek.|  
|**/fc**|Sucht oder erstellt die Zielanwendung.|  
|**/help**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|**/noreconfig**|Eine vorhandene Zielanwendung wird nicht neu konfiguriert.|  
|**/nologo**|Unterdrückt die Anzeige des Startbanners von Microsoft.|  
|**/parname:** *name*|Gibt den Namen oder die ID der zu suchenden oder zu erstellenden COM+-Anwendung an.|  
|**/reconfig**|Konfiguriert eine vorhandene Zielanwendung neu. Dies ist die Standardeinstellung.|  
|**/tlb:** *typelibraryfile*|Gibt die zu installierende Typbibliotheksdatei an.|  
|**/u**|Deinstalliert die Zielanwendung.|  
|**/quiet**|Gibt den stillen Modus an und unterdrückt das Logo und die Anzeige von Erfolgsmeldungen.|  
|**/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
## <a name="remarks"></a>Hinweise  
 Für „Regsvcs.exe“ ist eine von *assemblyFile.dll* angegebene Quelldatei für die Assembly erforderlich. Diese Assembly muss mit einem starken Namen signiert sein. Weitere Informationen zum Signieren mit starken Namen finden Sie unter [Signing an Assembly with a Strong Name (Signieren einer Assembly mit starkem Namen)](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md). Die Namen der Zielanwendung und der Typbibliothek sind optional. Das *applicationName*-Argument kann aus der Quelldatei für die Assembly generiert werden und wird von „Regsvcs.exe“ erstellt, sofern nicht bereits vorhanden. Über das *typelibraryfile*-Argument kann der Name einer Typbibliothek angeben werden. Wenn Sie keinen Typbibliotheksnamen angeben, verwendet "Regsvcs.exe" als Standardwert den Assemblynamen.  
  
 Wenn „Regsvcs.exe“ die Methoden einer Komponente registriert, unterliegt sie den [Forderungen](http://msdn.microsoft.com/en-us/e5283e28-2366-4519-b27d-ef5c1ddc1f48) und [Linkaufrufen](../../../docs/framework/misc/link-demands.md) für diese Methoden. Da das Tool in einer vollständig vertrauenswürdigen Umgebung ausgeführt wird, sind die meisten Forderungen nach einer Berechtigung erfolgreich. "Regsvcs.exe" kann jedoch keine Komponenten mit Methoden registrieren, die durch eine Forderung oder einen Linkaufruf für <xref:System.Security.Permissions.StrongNameIdentityPermission> oder <xref:System.Security.Permissions.PublisherIdentityPermission> geschützt sind.  
  
 Für die Verwendung von "Regsvcs.exe" benötigen Sie Administratorrechte auf dem lokalen Computer.  
  
 Wenn beim Ausführen einer dieser Aktionen ein Fehler auftritt, zeigt "Regsvcs.exe" entsprechende Fehlermeldungen an.  
  
## <a name="examples"></a>Beispiele  
 Der folgende Befehl fügt `myTest.dll` (eine vorhandene COM+-Anwendung) alle in `myTargetApp` enthaltenen öffentlichen Klassen hinzu und erstellt die Typbibliothek `myTest.tlb`.  
  
```  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 Der folgende Befehl fügt `myTest.dll` (eine vorhandene COM+-Anwendung) alle in `myTargetApp` enthaltenen öffentlichen Klassen hinzu und erstellt die Typbibliothek `newTest.tlb`.  
  
```  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Extras](../../../docs/framework/tools/index.md)  
 [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
