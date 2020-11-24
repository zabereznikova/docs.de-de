---
title: Laden von Daten aus einem Reader
ms.date: 03/30/2017
ms.assetid: 7e74918c-bc72-4977-a49b-e1520a6d8f60
ms.openlocfilehash: ea125e57dd6251a4fbd401bac8f37826083965b8
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822671"
---
# <a name="load-data-from-a-reader"></a>Laden von Daten aus einem Reader
Wenn ein XML-Dokument mithilfe der <xref:System.Xml.XmlDocument.Load%2A>-Methode und einem Parameter eines <xref:System.Xml.XmlReader> geladen wird, weist das Verhalten Unterschiede zu dem Verhalten auf, das beim Laden von Daten aus anderen Formaten eintritt. Wenn sich der Reader in seinem Ausgangszustand befindet, verarbeitet <xref:System.Xml.XmlDocument.Load%2A> den gesamten Inhalt des Readers und erstellt das XML-DOM (Dokumentobjektmodell) aus allen Daten im Reader.  
  
 Wenn sich der Reader bereits auf einem Knoten im Dokument befindet und der Reader an die <xref:System.Xml.XmlDocument.Load%2A>-Methode übergeben wird, versucht <xref:System.Xml.XmlDocument.Load%2A>, den aktuellen Knoten und alle zugehörigen nebengeordneten Elemente zu lesen. Dies erfolgt bis zum Endtag, das die aktuelle Hierarchietiefe abschließt. Ob <xref:System.Xml.XmlDocument.Load%2A> erfolgreich ist, hängt vom Knoten ab, auf dem sich der Reader beim Ladeversuch befindet, da <xref:System.Xml.XmlDocument.Load%2A> überprüft, ob das XML aus dem Reader wohlgeformt ist. Wenn das XML nicht wohlgeformt ist, löst <xref:System.Xml.XmlDocument.Load%2A> eine Ausnahme aus. In der folgende Gruppe von Knoten sind beispielsweise zwei Elemente der Stammebene enthalten, das XML ist nicht wohlgeformt und <xref:System.Xml.XmlDocument.Load%2A> löst eine Ausnahme aus.  
  
- Ein Kommentarknoten, auf den ein Elementknoten, ein weiterer Elementknoten und dann ein EndElement-Knoten folgt.  
  
 Die folgende Gruppe von Knoten erstellt ein unvollständiges DOM, da auf der Stammebene kein Element vorhanden ist.  
  
- Ein Kommentarknoten, auf den ein ProcessingInstruction-Knoten, ein Kommentarknoten und dann ein EndElement-Knoten folgt.  
  
 Dies löst keine Ausnahme aus, und die Daten werden geladen. Sie können an der obersten Position dieser Knoten ein Stammelement hinzufügen und wohlgeformtes XML erstellen, das ohne Fehler gespeichert werden kann.  
  
 Wenn sich der Reader auf einem Endknoten befindet, der für die Stammebene eines Dokuments ungültig ist (z. B. ein Leerraum- oder ein Attributknoten), setzt der Reader den Lesevorgang solange fort, bis er sich auf einem Knoten befindet, der als Stamm verwendet werden kann. Das Dokument beginnt an dieser Stelle mit dem Laden.  
  
 In der Standardeinstellung überprüft <xref:System.Xml.XmlDocument.Load%2A> nicht mithilfe der DTD (Document Type Definition) oder der Schemavalidierung, ob das XML gültig ist. Es wird nur überprüft, ob das XML wohlgeformt ist. Damit die Validierung ausgeführt wird, muss mithilfe der <xref:System.Xml.XmlReader>-Klasse ein <xref:System.Xml.XmlReaderSettings> erstellt werden. Die <xref:System.Xml.XmlReader>-Klasse kann die Validierung mithilfe der DTD oder des XSD-Schemas (Schema Definition Language) erzwingen. Die <xref:System.Xml.ValidationType>-Eigenschaft der <xref:System.Xml.XmlReaderSettings>-Klasse bestimmt, ob die <xref:System.Xml.XmlReader>-Instanz eine Validierung erzwingt. Weitere Informationen zum Überprüfen von XML-Daten finden Sie im Abschnitt Hinweise der <xref:System.Xml.XmlReader>-Referenzseite.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
