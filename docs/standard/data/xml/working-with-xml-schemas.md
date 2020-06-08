---
title: Arbeiten mit XML-Schemata
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: bbbcc70c-bf9a-4f6a-af72-1bab5384a187
ms.openlocfilehash: f239d67d959c1f7a0bfebfaaaa49de9cf9c9a111
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281686"
---
# <a name="working-with-xml-schemas"></a>Arbeiten mit XML-Schemata
Um die Struktur eines XML-Dokuments sowie dessen Elementbeziehungen, Datentypen und Inhaltseinschränkungen anzugeben, verwenden Sie eine DTD (Document Type Definition) oder ein XSD-Schema (XML Schema Definition Language). Obwohl ein XML-Dokument als wohlgeformt angesehen wird, wenn es alle syntaktischen Anforderungen erfüllt, die in der W3C-Empfehlung (World Wide Web Consortium) "Extensible Markup Language (XML) 1.0" definiert sind, ist es nur dann gültig, wenn es sowohl wohlgeformt ist als auch den Einschränkungen der DTD oder des Schemas entspricht. Das heißt, dass alle gültigen XML-Dokumente wohlgeformt sind, jedoch nicht alle wohlgeformten XML-Dokumente gültig sein müssen.  
  
 Weitere Informationen zu XML finden Sie unter [W3C XML 1.0 Recommendation](https://www.w3.org/TR/REC-xml/). Weitere Informationen zum XML-Schema finden Sie in den Empfehlungen [W3C XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/) und [W3C XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [XML Schema Object Model (SOM) (XML-Schemaobjektmodell (SOM))](xml-schema-object-model-som.md)  
 In diesem Abschnitt wird das Schema Object Model (SOM) im <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespace beschrieben, das eine Reihe von Klassen zur Verfügung stellt, mit denen Sie ein XSD-Schema aus einer Datei lesen oder programmgesteuert im Speicher ein Schema erstellen können.  
  
 [„XmlSchemaSet“ zur Kompilierung von Schemas](xmlschemaset-for-schema-compilation.md)  
 In diesem Abschnitt wird die <xref:System.Xml.Schema.XmlSchemaSet>-Klasse beschrieben, die als Cache fungiert, in dem XSD-Schemata gespeichert und validiert werden können.  
  
 [Pushbasierte Validierung mit „XmlSchemaValidator“](xmlschemavalidator-push-based-validation.md)  
 In diesem Abschnitt wird die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse beschrieben, die eine effiziente leistungsstarke Methode zum Validieren von XML-Daten anhand von XSD-Schemata in einem Push-Verfahren bereitstellt.  
  
 [Herleiten eines XML-Schemas](inferring-an-xml-schema.md)  
 In diesem Abschnitt wird das Verwenden der <xref:System.Xml.Schema.XmlSchemaInference>-Klasse zum Herleiten eines XSD-Schemas aus der Struktur eines XML-Dokuments beschrieben.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Validieren eines XML-Dokuments im DOM](validating-an-xml-document-in-the-dom.md)  
 In diesem Abschnitt wird das Validieren von XML im DOM (Document Object Model) beschrieben. Sie können das XML beim Laden in das DOM validieren, oder Sie validieren ein zuvor nicht validiertes XML-Dokument im DOM.  
  
 [Schemavalidierung mithilfe von „XPathNavigator“](schema-validation-using-xpathnavigator.md)  
 In diesem Abschnitt wird das Validieren von XML beschrieben, das mithilfe der <xref:System.Xml.XPath.XPathNavigator>-Klasse durchsucht und bearbeitet wurde.
