---
title: Ändern von Knoten, Inhalten und Werten in einem XML-Dokument
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 761773e0-db72-4986-b9f5-a522213d8397
ms.openlocfilehash: 4a53ba4fe16a3653b1be380da49e6b75cb347a28
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710673"
---
# <a name="modifying-nodes-content-and-values-in-an-xml-document"></a>Ändern von Knoten, Inhalten und Werten in einem XML-Dokument
Es gibt viele Möglichkeiten, die Knoten und den Inhalt eines Dokuments zu ändern. Sie haben folgende Möglichkeiten:  
  
- Den Wert von Knoten mithilfe der <xref:System.Xml.XmlNode.Value%2A>-Eigenschaft ändern.  
  
- Eine ganze Gruppe von Knoten durch Ersetzen der Knoten mit neuen Knoten ändern. Dies geschieht mithilfe der <xref:System.Xml.XmlNode.InnerXml%2A>-Eigenschaft.  
  
- Vorhandene Knoten mithilfe der <xref:System.Xml.XmlNode.RemoveChild%2A>-Methode durch neue Knoten ersetzen.  
  
- Den Knoten, die von der <xref:System.Xml.XmlCharacterData>-Klasse erben, mithilfe einer der Methoden <xref:System.Xml.XmlCharacterData.AppendData%2A>, <xref:System.Xml.XmlCharacterData.InsertData%2A> oder <xref:System.Xml.XmlCharacterData.ReplaceData%2A> zusätzliche Zeichen hinzufügen.  
  
- Inhalt ändern, indem ein Bereich von Zeichen mithilfe der <xref:System.Xml.XmlCharacterData.DeleteData%2A>-Methode von Knotentypen entfernt wird, die von <xref:System.Xml.XmlCharacterData> erben.  
  
 Eine einfache Möglichkeit zum Ändern des Werts eines Knotens bietet `node.Value = "new value";`. In der folgenden Tabelle ist aufgelistet, für welche Knotentypen diese einzelne Codezeile funktioniert und welche Daten des Knotentyps geändert wurden.  
  
|Knotentyp|Geänderte Daten|  
|---------------|------------------|  
|Attribute|Der Wert des Attributs.|  
|CDATASection|Der Inhalt von CDATASection.|  
|Anmerkungen|Der Inhalt des Kommentars.|  
|ProcessingInstruction|Der Inhalt mit Ausnahme des Ziels.|  
|Text|Der Inhalt des Texts.|  
|XmlDeclaration|Der Inhalt der Deklaration, ausgenommen das `<?xml`-Markup und das `?>`-Markup.|  
|Whitespace|Der Wert des Leerraums. Sie können festlegen, dass der Wert einer der vier erkannten XML-Leerraumzeichen ist: Leerzeichen, Tabulator, Wagenrücklauf oder Zeilenvorschub.|  
|SignificantWhitespace|Der Wert des signifikanten Leerraums. Sie können festlegen, dass der Wert einer der vier erkannten XML-Leerraumzeichen ist: Leerzeichen, Tabulator, Wagenrücklauf oder Zeilenvorschub.|  
  
 Alle nicht in der Tabelle aufgelisteten Knotentypen sind keine gültigen Knotentypen, für die ein Wert festgelegt werden kann. Durch Festlegen eines Werts für einen anderen Knotentyp wird eine <xref:System.InvalidOperationException> ausgelöst.  
  
 Die <xref:System.Xml.XmlNode.InnerXml%2A>-Eigenschaft ändert das Markup der untergeordneten Knoten des aktuellen Knotens. Durch Festlegen dieser Eigenschaft werden die untergeordneten Knoten durch analysierten Inhalt der angegebenen Zeichenfolge ersetzt. Die Analyse wird im Kontext des aktuellen Namespaces durchgeführt. Zusätzlich entfernt <xref:System.Xml.XmlNode.InnerXml%2A> redundante Namespacedeklarationen. Daher wird die Größe des Dokuments nicht mit redundanten Namespacedeklarationen erhöht, wenn zahlreiche Ausschneide- und Einfügevorgänge erfolgen. Ein Codebeispiel, das die Auswirkungen von Namespaces auf die <xref:System.Xml.XmlNode.InnerXml%2A>-Operation veranschaulicht, finden Sie unter der <xref:System.Xml.XmlDocument.InnerXml%2A>-Eigenschaft.  
  
 Beim Verwenden der <xref:System.Xml.XmlCharacterData.ReplaceData%2A>-Methode und der <xref:System.Xml.XmlNode.RemoveChild%2A>-Methode werden die ersetzten oder entfernten Knoten von der Methode zurückgegeben. Dieser Knoten kann an einer anderen Position im XML-DOM (Dokumentobjektmodell) wieder eingefügt werden. Die <xref:System.Xml.XmlCharacterData.ReplaceData%2A>-Methode führt zwei Validierungen des Knotens durch, der in das Dokument eingefügt wird. Bei der ersten Validierung wird sichergestellt, dass der Knoten dem Knoten untergeordnet wird, der untergeordnete Knoten dieses Typs aufweisen kann. Bei der zweiten Validierung wird sichergestellt, dass der eingefügte Knoten kein indirekt übergeordneter Knoten des Knotens ist, dem er untergeordnet wird. Ist eine dieser Bedingungen nicht erfüllt, wird eine <xref:System.InvalidOperationException> ausgelöst.  
  
 Das Hinzufügen oder Entfernen von schreibgeschützten untergeordneten Elementen eines Knotens, der bearbeitet werden kann, ist ein gültiger Vorgang. Durch Versuche, den schreibgeschützten Knoten selbst zu ändern, wird eine <xref:System.InvalidOperationException> ausgelöst. Ein Bespiel dafür ist das Verändern der untergeordneten Elemente eines <xref:System.Xml.XmlEntityReference>-Knotens. Die untergeordneten Elemente sind schreibgeschützt und können nicht verändert werden. Durch einen Versuch, diese zu verändern, wird eine <xref:System.InvalidOperationException> ausgelöst.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
