---
title: Serialisierung (C#) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 704ff2bf-02ab-4fea-94ea-594107825645
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2deffa4f2c9a407b74e8bc6357afc9400a3ba7d4
ms.lasthandoff: 03/13/2017

---
# <a name="serialization-c-"></a>Serialisierung (C#)
Serialisierung ist der Prozess der Konvertierung eines Objekts in einen Stream von Bytes zum Speichern des Objekts oder zum Übertragen in den Arbeitsspeicher, eine Datenbank oder eine Datei. Der Hauptzweck ist das Speichern des Zustands eines Objekts, um es bei Bedarf neu erstellen zu können. Der Umkehrvorgang wird als Deserialisierung bezeichnet.  
  
## <a name="how-serialization-works"></a>Funktionsweise der Serialisierung  
 Diese Abbildung zeigt den gesamten Ablauf der Serialisierung.  
  
 ![Grafik zur Serialisierung](../../../../csharp/programming-guide/concepts/serialization/media/serialization.gif "Serialisierung")  
  
 Das Objekt wird in einen Stream serialisiert, der nicht nur die Daten, sondern auch Informationen über den Typ des Objekts enthält, wie Version, Kultur und Assemblynamen. Von diesem Stream aus kann es in einer Datenbank, einer Datei oder einem Arbeitsspeicher gespeichert werden.  
  
### <a name="uses-for-serialization"></a>Nutzungsszenarien für die Serialisierung  
 Die Serialisierung ermöglicht dem Entwickler das Speichern des Zustands eines Objekts und bei Bedarf das erneute Erstellen, das Bereitstellen von Speicher für Objekte sowie für den Datenaustausch. Über die Serialisierung kann ein Entwickler Aktionen durchführen wie das Senden des Objekts an eine Remoteanwendung mithilfe eines Web Service, das Übergeben eines Objekts von einer Domäne an eine andere, das Übergeben eines Objekts über eine Firewall als XML-Zeichenfolge oder das anwendungsübergreifende Verwalten der Sicherheit oder benutzerspezifischer Informationen.  
  
### <a name="making-an-object-serializable"></a>Ein Objekt serialisierbar machen  
 Zum Serialisieren eines Objekts benötigen Sie das entsprechende Objekt, einen Stream, der das serialisierte Objekt enthält und ein <xref:System.Runtime.Serialization.Formatter>-Element. <xref:System.Runtime.Serialization> enthält die erforderlichen Klassen zum Serialisieren und Deserialisieren von Objekten.  
  
 Wenden Sie das <xref:System.SerializableAttribute>-Attribut auf einen Typ an, um anzugeben, dass Instanzen dieses Typs serialisiert werden können. Eine <xref:System.Runtime.Serialization.SerializationException>-Ausnahme wird ausgelöst, wenn Sie versuchen, eine Serialisierung durchzuführen, aber der Typ kein <xref:System.SerializableAttribute>-Attribut aufweist.  
  
 Wenn ein Feld innerhalb Ihrer Klasse nicht serialisierbar sein soll, wenden Sie das <xref:System.NonSerializedAttribute>-Attribut an. Wenn ein Feld eines serialisierbaren Typs einen Zeiger, einen Ziehpunkt oder eine andere Datenstruktur enthält, der/die für eine bestimmte Umgebung spezifisch ist, und das Feld in keiner anderen Umgebung sinnvoll wiederhergestellt werden kann, sollten Sie seine Serialisierbarkeit deaktivieren.  
  
 Wenn eine serialisierte Klasse Verweise auf Objekte anderer Klassen enthält, die mit <xref:System.SerializableAttribute> markiert sind, werden diese Objekte ebenfalls serialisiert.  
  
## <a name="binary-and-xml-serialization"></a>Binär- und XML-Serialisierung  
 Die Binär- oder XML-Serialisierung kann verwendet werden. Bei der binären Serialisierung werden alle Member einschließlich der schreibgeschützten Member serialisiert und die Leistung wird verbessert. Die XML-Serialisierung bietet besser lesbaren Code sowie größere Flexibilität bei der Objektfreigabe und bei der Nutzung zu Interoperabilitätszwecken.  
  
### <a name="binary-serialization"></a>Binäre Serialisierung  
 Die binäre Serialisierung verwendet zum Generieren einer kompakten Serialisierung die binäre Codierung für den Speicher oder für socketbasierte Netzwerkstreams.  
  
### <a name="xml-serialization"></a>XML-Serialisierung  
 Bei der XML-Serialisierung werden die öffentlichen Felder und Eigenschaften eines Objekts bzw. die Parameter und Rückgabewerte von Methoden in einen XML-Stream serialisiert, der einem bestimmtem XSD-Dokument (XML Schema Definition) entspricht. Die XML-Serialisierung führt zu stark typisierten Klassen mit öffentlichen Eigenschaften und Feldern, die in XML konvertiert werden. „<xref:System.Xml.Serialization>“ enthält die erforderlichen Klassen zum Serialisieren und Deserialisieren von XML-Code.  
  
 Sie können Attribute auf Klassen und Klassenmember anwenden, um die Art der Serialisierung oder Deserialisierung einer Instanz der Klasse durch „<xref:System.Xml.Serialization.XmlSerializer>“ zu steuern.  
  
## <a name="basic-and-custom-serialization"></a>Grundlegende und benutzerdefinierte Serialisierung  
 Die Serialisierung kann auf zwei Arten ausgeführt werden: grundlegend und benutzerdefiniert. Die grundlegende Serialisierung verwendet .NET Framework, um die Serialisierung des Objekts zu automatisieren.  
  
### <a name="basic-serialization"></a>Einfache Serialisierung  
 Die einzige Anforderung bei der grundlegenden Serialisierung ist, dass das <xref:System.SerializableAttribute>-Attribut auf das Objekt angewendet werden muss. Das <xref:System.NonSerializedAttribute>-Attribut kann verwendet werden, um die Serialisierung spezifischer Felder zu verhindern.  
  
 Wenn Sie die grundlegende Serialisierung verwenden, kann die Versionsverwaltung zu Problemen führen. In diesem Fall wird die benutzerdefinierte Serialisierung bevorzugt. Die grundlegende Serialisierung ist die einfachste Möglichkeit zur Serialisierung, bietet allerdings nicht viel Kontrolle über den Prozess.  
  
### <a name="custom-serialization"></a>Benutzerdefinierte Serialisierung  
 Bei der benutzerdefinierten Serialisierung können Sie genau angeben, welche Objekte serialisiert werden und wie sie ausgeführt wird. Die Klasse muss mit „<xref:System.SerializableAttribute>“ markiert werden und die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementieren.  
  
 Wenn das Objekt ebenso auf benutzerdefinierte Weise deserialisiert werden soll, müssen Sie einen benutzerdefinierten Konstruktor verwenden.  
  
## <a name="designer-serialization"></a>Designerserialisierung  
 Die Designerserialisierung ist eine besondere Form der Serialisierung, die die Art der Objektpersistenz einbezieht, die den Entwicklungstools in der Regel zugeordnet ist. Bei der Designerserialisierung handelt es sich um den Prozess der Konvertierung eines Objektdiagramms in eine Quelldatei, die später zum Wiederherstellen des Objektdiagramms verwendet werden kann. Eine Quelldatei kann Code, Markup oder sogar SQL-Tabelleninformationen enthalten.  
  
##  <a name="BKMK_RelatedTopics"></a> Verwandte Themen und Beispiele  
 [Walkthrough: Persisting an Object in Visual Studio (C#)](../../../../csharp/programming-guide/concepts/serialization/walkthrough-persisting-an-object-in-visual-studio.md) (Exemplarische Vorgehensweise: Beibehalten eines Objekts in Visual Studio (C#))  
 Veranschaulicht, wie die Serialisierung verwendet werden kann, um die Daten eines Objekts zwischen Instanzen beizubehalten. Dadurch können Sie Werte speichern und abrufen, wenn das Objekt das nächste Mal instanziiert wird.  
  
 [How to: Read Object Data from an XML File (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) (Vorgehensweise: Lesen von Objektdaten aus einer XML-Datei (C#))  
 Zeigt, wie Objektdaten gelesen werden, die zuvor mit der <xref:System.Xml.Serialization.XmlSerializer>-Klasse in eine XML-Datei geschrieben wurden.  
  
 [How to: Write Object Data to an XML File (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) (Vorgehensweise: Schreiben von Objektdaten in eine XML-Datei (C#))  
 Zeigt, wie das Objekt mit der <xref:System.Xml.Serialization.XmlSerializer>-Klasse von einer Klasse in eine XML-Datei geschrieben wird.
