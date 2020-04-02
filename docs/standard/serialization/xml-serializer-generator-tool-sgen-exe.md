---
title: XML Serializer Generator-Tool (Sgen.exe)
ms.date: 03/30/2017
ms.assetid: cc1d1f1c-fb26-4be9-885a-3fe84c81cec6
ms.openlocfilehash: bc1a0abaeef9a9244aa83941e590063c7ef167d1
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588360"
---
# <a name="xml-serializer-generator-tool-sgenexe"></a>XML Serializer Generator-Tool (Sgen.exe)

Der XML Serializer Generator erstellt eine XML-Serialisierungsassembly für Typen in einer angegebenen Assembly. Die Serialisierungsassembly verbessert die <xref:System.Xml.Serialization.XmlSerializer> Startleistung eines, wenn sie Objekte der angegebenen Typen serialisiert oder deserialisiert.
  
## <a name="syntax"></a>Syntax

Führen Sie das Werkzeug über die Befehlszeile aus.
  
```console  
sgen [options]  
```
  
> [!TIP]
> Damit .NET Framework-Tools ordnungsgemäß funktionieren, `Path` `Include`müssen `Lib` Sie ihre , - und Umgebungsvariablen richtig festlegen. Führen Sie zum Festlegen dieser Umgebungsvariablen die Datei „SDKVars.bat“ aus, die sich im Verzeichnis „\<SDK>\v2.0\Bin“ befindet. SDKVars.bat muss in jeder Befehlsshell ausgeführt werden.
  
## <a name="parameters"></a>Parameter  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/a\[ssembly\]:**_Dateiname_|Generiert den Serialisierungscode für alle Typen, die in der durch *filename* angegebenen Assembly oder ausführbaren Datei enthalten sind. Nur ein Dateiname kann bereitgestellt werden. Bei Wiederholung dieses Arguments wird der letzte Dateiname verwendet.|  
|**/c\[\]ompiler :**_Optionen_|Gibt die Optionen für die Übergabe an den C#-Compiler an. Bei Übergabe an den Compiler werden alle csc.exe-Optionen unterstützt. Damit kann angegeben werden, dass die Assembly signiert werden soll. Außerdem kann die Schlüsseldatei angegeben werden.|  
|**/d\[ebug\]**|Generiert ein Image, das mit einem Debugger verwendet werden kann.|  
|**/f\[orce\]**|Erzwingt das Überschreiben einer vorhandenen, gleichnamigen Assembly. Der Standardwert ist **false**.|  
|**/help oder /?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|**/k\[eep\]**|Unterdrückt das Löschen der generierten Quelldateien und anderer temporärer Dateien, nachdem sie in die Serialisierungsassembly kompiliert wurden. Damit kann ermittelt werden, ob das Tool für einen bestimmten Typ Serialisierungscode generiert.|  
|**/n\[ologo\]**|Unterdrückt die Anzeige des Startbanners von Microsoft.|  
|**/o\[\]ut :**_Pfad_|Gibt das Verzeichnis an, in das die generierte Assembly gespeichert werden soll. **Hinweis:** Der Name der generierten Assembly besteht aus dem Namen der Eingabeassembly plus „xmlSerializers.dll“.|  
|**/p\[roxytypen\]**|Generiert Serialisierungscode nur für die Proxytypen des XML-Webdiensts.|  
|**/r\[eference\]:**_Assemblydateien_|Gibt die Assemblys an, auf die von den Typen, die XML-Serialisierung erfordern, verwiesen wird. Akzeptiert mehrere Assemblydateien, die durch Kommas getrennt werden.|  
|**/s\[ilent\]**|Unterdrückt die Anzeige von Erfolgsmeldungen.|  
|**/t\[\]ype :**_Typ_|Generiert Serialisierungscode nur für den angegebenen Typ.|  
|**/v\[erbose\]**|Zeigt eine ausführliche Ausgabe für das Debuggen an. Listet Typen aus der Zielassembly auf, die nicht mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können.|  
|**/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn der XML Serializer Generator nicht verwendet wird, generiert <xref:System.Xml.Serialization.XmlSerializer> bei jeder Ausführung einer Anwendung für jeden Typ Serialisierungscode und eine Serialisierungsassembly. Um die Leistung des XML-Serialisierungsstarts zu verbessern, verwenden Sie das Tool Sgen.exe, um diese Assemblys im Voraus zu generieren. Diese Assemblys können dann zusammen mit der Anwendung bereitgestellt werden.  
  
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

- [Tools](../../../docs/framework/tools/index.md)
- [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
