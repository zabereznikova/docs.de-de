---
title: XML Serializer Generator-Tool (Sgen.exe)
description: Das XML Serializer Generator-Tool erstellt eine XML-Serialisierungsassembly zur Verbesserung der Startleistung von XmlSerializer für Typen in einer Assembly.
ms.date: 03/30/2017
ms.assetid: cc1d1f1c-fb26-4be9-885a-3fe84c81cec6
ms.openlocfilehash: c2f33236e39f61638118f45f0d5ab5385df27ac3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676516"
---
# <a name="xml-serializer-generator-tool-sgenexe"></a>XML Serializer Generator-Tool (Sgen.exe)

Das XML Serializer Generator-Tool erstellt eine XML-Serialisierungsassembly für Typen in einer angegebenen Assembly. Die Serialisierungsassembly verbessert die Startleistung einer <xref:System.Xml.Serialization.XmlSerializer>, wenn diese Objekte der angegebenen Typen serialisiert oder deserialisiert.
  
## <a name="syntax"></a>Syntax

Führen Sie das Tool über die Befehlszeile aus.
  
```console  
sgen [options]  
```
  
> [!TIP]
> Damit .NET Framework-Tools einwandfrei funktionieren, müssen die Umgebungsvariablen `Path`, `Include` und `Lib` korrekt festgelegt sein. Führen Sie zum Festlegen dieser Umgebungsvariablen die Datei „SDKVars.bat“ im Verzeichnis „\<SDK>\\\<version>\Bin“ aus. SDKVars.bat muss in jeder Befehlsshell ausgeführt werden.
  
## <a name="parameters"></a>Parameter  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**/a\[ssembly\]:** _Dateiname_|Generiert den Serialisierungscode für alle Typen, die in der durch *filename* angegebenen Assembly oder ausführbaren Datei enthalten sind. Nur ein Dateiname kann bereitgestellt werden. Bei Wiederholung dieses Arguments wird der letzte Dateiname verwendet.|  
|**/c\[ompiler\]:** _Optionen_|Gibt die Optionen für die Übergabe an den C#-Compiler an. Bei Übergabe an den Compiler werden alle csc.exe-Optionen unterstützt. Damit kann angegeben werden, dass die Assembly signiert werden soll. Außerdem kann die Schlüsseldatei angegeben werden.|  
|**/d\[ebug\]**|Generiert ein Image, das mit einem Debugger verwendet werden kann.|  
|**/f\[orce\]**|Erzwingt das Überschreiben einer vorhandenen, gleichnamigen Assembly. Der Standardwert ist **FALSE**.|  
|**/help oder /?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|**/k\[eep\]**|Unterdrückt das Löschen der generierten Quelldateien und anderer temporärer Dateien, nachdem sie in die Serialisierungsassembly kompiliert wurden. Damit kann ermittelt werden, ob das Tool für einen bestimmten Typ Serialisierungscode generiert.|  
|**/n\[ologo\]**|Unterdrückt die Anzeige des Startbanners von Microsoft.|  
|**/o\[ut\]:** _Pfad_|Gibt das Verzeichnis an, in das die generierte Assembly gespeichert werden soll. **Hinweis**:  Der Name der generierten Assembly besteht aus dem Namen der Eingabeassembly plus "xmlSerializers.dll".|  
|**/p\[roxytypes\]**|Generiert Serialisierungscode nur für die Proxytypen des XML-Webdiensts.|  
|**/r\[eference\]:** _Assemblydateien_|Gibt die Assemblys an, auf die von den Typen, die XML-Serialisierung erfordern, verwiesen wird. Akzeptiert mehrere Assemblydateien, die durch Kommas getrennt werden.|  
|**/s\[ilent\]**|Unterdrückt die Anzeige von Erfolgsmeldungen.|  
|**/t\[ype\]:** _Typ_|Generiert Serialisierungscode nur für den angegebenen Typ.|  
|**/v\[erbose\]**|Zeigt eine ausführliche Ausgabe für das Debuggen an. Listet Typen aus der Zielassembly auf, die nicht mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können.|  
|**/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
## <a name="remarks"></a>Hinweise  

 Wenn der XML Serializer Generator nicht verwendet wird, generiert <xref:System.Xml.Serialization.XmlSerializer> bei jeder Ausführung einer Anwendung für jeden Typ Serialisierungscode und eine Serialisierungsassembly. Verwenden Sie für eine bessere Leistung beim Starten der XML-Serialisierung das Tool Sgen.exe, um die Assemblys im Voraus zu generieren. Diese Assemblys können dann zusammen mit der Anwendung bereitgestellt werden.  
  
 Mit dem XML Serializer Generator kann auch die Leistung von Clients, die zur Kommunikation mit Servern XML-Webdienstproxys verwenden, verbessert werden, da die Leistung durch den Serialisierungsprozess beim erstmaligen Laden des Typs nicht beeinträchtigt wird.  
  
 Die generierten Assemblys können nicht auf der Serverseite eines Webdiensts verwendet werden. Dieses Tool wird nur für Webdienstclients und manuelle Serialisierungsszenarien verwendet.  
  
 Wenn der Name der Assembly, die den zu serialisierenden Typen enthält, MyType.dll ist, erhält die zugehörige Serialisierungsassembly den Namen MyType.XmlSerializers.dll.  
  
## <a name="examples"></a>Beispiele  

 Mit dem folgenden Befehl wird eine Assembly mit dem Namen Data.XmlSerializers.dll erstellt, um alle in der Assembly Data.dll enthaltenen Typen zu serialisieren.  
  
```console  
sgen Data.dll
```  
  
 Auf die Assembly Data.XmlSerializers.dll kann vom Code verwiesen werden, der die Typen in Data.dll serialisiert und deserialisiert.  
  
## <a name="see-also"></a>Siehe auch

- [Extras](../../framework/tools/index.md)
- [Eingabeaufforderungen](../../framework/tools/developer-command-prompt-for-vs.md)
