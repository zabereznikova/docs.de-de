---
title: XML Serializer Generator-Tool (Sgen.exe)
ms.date: 03/30/2017
ms.assetid: cc1d1f1c-fb26-4be9-885a-3fe84c81cec6
ms.openlocfilehash: 492337973f71b10dc061353b7083f596b402ae29
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392706"
---
# <a name="xml-serializer-generator-tool-sgenexe"></a>XML Serializer Generator-Tool (Sgen.exe)
Der XML Serializer Generator erstellt eine XML-Serialisierungsassembly für die Typen in einer bestimmten Assembly, um die Startleistung von <xref:System.Xml.Serialization.XmlSerializer> beim Serialisieren oder Deserialisieren von Objekten der angegebenen Typen zu erhöhen.  
  
## <a name="syntax"></a>Syntax  
  
```console  
sgen [options]  
```  
  
## <a name="parameters"></a>Parameter  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**/a @ no__t-1ssembly @ no__t-2:** _Dateiname_|Generiert den Serialisierungscode für alle Typen, die in der durch *filename* angegebenen Assembly oder ausführbaren Datei enthalten sind. Nur ein Dateiname kann bereitgestellt werden. Bei Wiederholung dieses Arguments wird der letzte Dateiname verwendet.|  
|**/c @ no__t-1ompiler @ no__t-2:** _Optionen_|Gibt die Optionen für die Übergabe an den C#-Compiler an. Bei Übergabe an den Compiler werden alle csc.exe-Optionen unterstützt. Damit kann angegeben werden, dass die Assembly signiert werden soll. Außerdem kann die Schlüsseldatei angegeben werden.|  
|**/d @ no__t-1ebug @ no__t-2**|Generiert ein Image, das mit einem Debugger verwendet werden kann.|  
|**/f @ no__t-1orce @ no__t-2**|Erzwingt das Überschreiben einer vorhandenen, gleichnamigen Assembly. Der Standardwert ist **FALSE**.|  
|**/help oder /?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|**/k @ no__t-1eep @ no__t-2**|Unterdrückt das Löschen der generierten Quelldateien und anderer temporärer Dateien, nachdem sie in die Serialisierungsassembly kompiliert wurden. Damit kann ermittelt werden, ob das Tool für einen bestimmten Typ Serialisierungscode generiert.|  
|**/n @ no__t-1ologo @ no__t-2**|Unterdrückt die Anzeige des Startbanners von Microsoft.|  
|**/o @ no__t-1UT @ no__t-2:** _Pfad_|Gibt das Verzeichnis an, in das die generierte Assembly gespeichert werden soll. **Hinweis**:  Der Name der generierten Assembly besteht aus dem Namen der Eingabeassembly plus "xmlSerializers.dll".|  
|**/p\[roxytypes\]**|Generiert Serialisierungscode nur für die Proxytypen des XML-Webdiensts.|  
|**/r\[eference\]:** _assemblyfiles_|Gibt die Assemblys an, auf die von den Typen, die XML-Serialisierung erfordern, verwiesen wird. Akzeptiert mehrere Assemblydateien, die durch Kommas getrennt werden.|  
|**/s @ no__t-1ilent @ no__t-2**|Unterdrückt die Anzeige von Erfolgsmeldungen.|  
|**/t @ no__t-1ype @ no__t-2:** _Type_|Generiert Serialisierungscode nur für den angegebenen Typ.|  
|**/v @ no__t-1erbose @ no__t-2**|Zeigt eine ausführliche Ausgabe für das Debuggen an. Listet Typen aus der Zielassembly auf, die nicht mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können.|  
|**/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn der XML Serializer Generator nicht verwendet wird, generiert <xref:System.Xml.Serialization.XmlSerializer> bei jeder Ausführung einer Anwendung für jeden Typ Serialisierungscode und eine Serialisierungsassembly. Um die Leistung des Starts der XML-Serialisierung zu verbessern, verwenden Sie das Tool Sgen. exe, um diese Assemblys vorab zu generieren. Diese Assemblys können dann zusammen mit der Anwendung bereitgestellt werden.  
  
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
