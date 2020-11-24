---
title: Übersicht über das XML-Schemaobjektmodell (SOM)
ms.date: 03/30/2017
ms.assetid: 896a1e12-5655-42c6-8cdd-89c12862b34b
ms.openlocfilehash: c54f92ede64e59478a0e9bfd919666caa9481137
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819213"
---
# <a name="xml-schema-object-model-overview"></a>Übersicht über das XML-Schemaobjektmodell (SOM)
Das SOM (Schemaobjektmodell) in Microsoft .NET Framework ist eine umfangreiche API, mit der Sie Schemata programmgesteuert erstellen, bearbeiten und validieren können. Das SOM arbeitet mit XML-Schemadokumenten auf ähnliche Weise, wie das DOM (Document Object Model) mit XML-Dokumenten arbeitet. XML-Schemadokumente sind gültige XML-Dateien, die sobald sie in das SOM geladen werden, eine Bedeutung zur Struktur und Gültigkeit von anderen XML-Dokumenten tragen, die dem Schema entsprechen.  
  
 Ein Schema ist ein XML-Dokument, dass eine Klasse von XML-Dokumenten definiert, indem die Struktur oder das Modell von XML-Dokumenten für ein bestimmtes Schema angegeben wird. Ein Schema gibt die Einschränkungen des Inhalts der XML-Dokumente an und beschreibt das Vokabular (Regeln oder Grammatik), dem kompatible XML-Dokumente folgen müssen, um für dieses bestimmte Schema gültig zu sein. Die Validierung eines XML-Dokuments ist der Vorgang, durch den sichergestellt wird, dass das Dokument der vom Schema angegebenen Grammatik entspricht.  
  
 In .NET Framework bietet Ihnen die SOM API die folgenden Möglichkeiten zum Erstellen, Bearbeiten und Validieren von Schemata.  
  
- Laden und Speichern gültiger Schemata in und aus Dateien.  
  
- Erstellen von speicherinternen Schemata mithilfe stark typisierter Klassen.  
  
- Interagieren mit der <xref:System.Xml.Schema.XmlSchemaSet>-Klasse zum Zwischenspeichern, Kompilieren und Abrufen von Schemata.  
  
- Interagieren mit der <xref:System.Xml.XmlReader.Create%2A>-Methode der <xref:System.Xml.XmlReader>-Klasse zum Validieren von XML-Instanzdokumenten anhand von Schemata.  
  
- Erstellen von Editoren zum Erstellen und Verwalten von Schemata.  
  
- Dynamisches Bearbeiten eines Schemas, das zur Verwendung beim Validieren eines XML-Instanzdokuments kompiliert und gespeichert werden kann.  
  
## <a name="the-schema-object-model"></a>Das Schemaobjektmodell (SOM)  
 Das SOM besteht aus zahlreichen Klassen im <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespace, die den Elementen in einem XML-Schema entsprechen. Das `<xsd:schema>...</xsd:schema>`-Element wird beispielsweise der <xref:System.Xml.Schema.XmlSchema?displayProperty=nameWithType>-Klasse zugeordnet, und alle Informationen, die in einem `<xsd:schema/>`-Element enthalten sein können, können mit der <xref:System.Xml.Schema.XmlSchema>-Klasse dargestellt werden. Auf ähnliche Weise werden das `<xsd:element>...</xsd:element>`-Element und `<xsd:attribute>...</xsd:attribute>`-Element der <xref:System.Xml.Schema.XmlSchemaElement?displayProperty=nameWithType>-Klasse bzw. der <xref:System.Xml.Schema.XmlSchemaAttribute?displayProperty=nameWithType>-Klasse zugeordnet. Diese Zuordnung wird für alle Elemente eines XML-Schemas vorgenommen, wodurch ein XML-Schemaobjektmodell im <xref:System.Xml.Schema>-Namespace erstellt wird. Dies wird im folgenden Diagramm veranschaulicht.  
  
 ![System.Xml.Schema-Objektmodell](./media/xml-schema-object-model-overview/xml-schema-object-model.gif)  
  
 Weitere Informationen zu den einzelnen Klassen im <xref:System.Xml.Schema>-Namespace finden Sie in der Referenzdokumentation zum <xref:System.Xml.Schema>-Namespace in der .NET Framework-Klassenbibliothek.  
  
## <a name="see-also"></a>Siehe auch

- [Lesen und Schreiben von XML-Schemas](reading-and-writing-xml-schemas.md)
- [Erstellen von XML-Schemas](building-xml-schemas.md)
- [Durchlaufen von XML-Schemas](traversing-xml-schemas.md)
- [Bearbeiten von XML-Schemas](editing-xml-schemas.md)
- [Einfügen oder Importieren von XML-Schemas](including-or-importing-xml-schemas.md)
- [„XmlSchemaSet“ zur Kompilierung von Schemas](xmlschemaset-for-schema-compilation.md)
- [Post-Schema-Compilation-Infoset](post-schema-compilation-infoset.md)
