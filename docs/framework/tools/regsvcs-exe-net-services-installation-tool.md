---
title: Regsvcs.exe (.NET Services Installation-Tool)
description: Verwenden Sie „Regsvcs.exe“, das .NET-Dienstinstallationstool. Laden und registrieren Sie eine Assembly, konfigurieren Sie Dienste, die Sie einer Klasse programmgesteuert hinzugefügt haben, und vielesmehr.
ms.date: 03/30/2017
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
ms.openlocfilehash: 474018b8bc39e4d5c36bd4bc6481072b218d6270
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558393"
---
# <a name="regsvcsexe-net-services-installation-tool"></a>Regsvcs.exe (.NET Services Installation-Tool)
Mit dem .NET Services Installation-Tool können folgende Aktionen ausgeführt werden:  
  
- Laden und Registrieren einer Assembly  
  
- Generieren, Registrieren und Installieren einer Typbibliothek in einer angegebenen COM+-Anwendung  
  
- Konfigurieren von Diensten, die Sie programmgesteuert einer Klasse hinzugefügt haben  
  
 Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```console  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll
```  
  
## <a name="parameters"></a>Parameter  
  
|Argument|BESCHREIBUNG|  
|--------------|-----------------|  
|*assemblyFile.dll*|Die Quelldatei für die Assembly. Die Assembly muss mit einem starken Namen signiert sein. Weitere Informationen dazu finden Sie unter [Signing an Assembly with a Strong Name (Signieren einer Assembly mit starkem Namen)](../../standard/assembly/sign-strong-name.md).|  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/appdir:** *path*|Gibt das Stammverzeichnis der Anwendung an.|  
|**/appname:** *applicationName*|Gibt den Namen der zu suchenden oder zu erstellenden COM+-Anwendung an.|  
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
 Für „Regsvcs.exe“ ist eine von *assemblyFile.dll* angegebene Quelldatei für die Assembly erforderlich. Diese Assembly muss mit einem starken Namen signiert sein. Weitere Informationen zum Signieren mit starken Namen finden Sie unter [Signing an Assembly with a Strong Name (Signieren einer Assembly mit starkem Namen)](../../standard/assembly/sign-strong-name.md). Die Namen der Zielanwendung und der Typbibliothek sind optional. Das *applicationName*-Argument kann aus der Quelldatei für die Assembly generiert werden und wird von „Regsvcs.exe“ erstellt, sofern nicht bereits vorhanden. Über das *typelibraryfile*-Argument kann der Name einer Typbibliothek angeben werden. Wenn Sie keinen Typbibliotheksnamen angeben, verwendet "Regsvcs.exe" als Standardwert den Assemblynamen.  
  
 Wenn „Regsvcs.exe“ die Methoden einer Komponente registriert, unterliegt sie den [Forderungen](/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) und [Linkaufrufen](../misc/link-demands.md) für diese Methoden. Da das Tool in einer vollständig vertrauenswürdigen Umgebung ausgeführt wird, sind die meisten Forderungen nach einer Berechtigung erfolgreich. "Regsvcs.exe" kann jedoch keine Komponenten mit Methoden registrieren, die durch eine Forderung oder einen Linkaufruf für <xref:System.Security.Permissions.StrongNameIdentityPermission> oder <xref:System.Security.Permissions.PublisherIdentityPermission> geschützt sind.  
  
 Für die Verwendung von "Regsvcs.exe" benötigen Sie Administratorrechte auf dem lokalen Computer.  
  
 Wenn beim Ausführen einer dieser Aktionen ein Fehler auftritt, zeigt "Regsvcs.exe" entsprechende Fehlermeldungen an.  
  
## <a name="examples"></a>Beispiele  
 Der folgende Befehl fügt `myTest.dll` (eine vorhandene COM+-Anwendung) alle in `myTargetApp` enthaltenen öffentlichen Klassen hinzu und erstellt die Typbibliothek `myTest.tlb`.  
  
```console  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 Der folgende Befehl fügt `myTest.dll` (eine vorhandene COM+-Anwendung) alle in `myTargetApp` enthaltenen öffentlichen Klassen hinzu und erstellt die Typbibliothek `newTest.tlb`.  
  
```console  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a>Siehe auch

- [Extras](index.md)
- [How to: Signieren einer Assembly mit einem starken Namen](../../standard/assembly/sign-strong-name.md)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
