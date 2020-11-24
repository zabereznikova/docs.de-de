---
title: In ein Dokument eingebettete Stylesheetdirektiven
ms.date: 03/30/2017
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
ms.openlocfilehash: 25946fd14a82428ae4367cd33511df68e9929203
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818569"
---
# <a name="style-sheet-directives-embedded-in-a-document"></a>In ein Dokument eingebettete Stylesheetdirektiven

Gelegentlich enthält vorhandener XML-Code die Stylesheetanweisung `<?xml:stylesheet?>`. Microsoft Internet Explorer akzeptiert diese als Alternative zur `<?xml-stylesheet?>`-Syntax. Wenn die XML-Daten, wie im Folgenden dargestellt, eine `<?xml:stylesheet?>`-Anweisung enthalten, wird durch den Versuch, diese Daten in das Dokumentobjektmodell (DOM) zu laden, eine Ausnahme ausgelöst.

```xml
<?xml version="1.0" ?>
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>
<root>
    <test>Node 1</test>
    <test>Node 2</test>
</root>
```

Der Grund hierfür ist, dass `<?xml:stylesheet?>` als ungültige **ProcessingInstruction** für das DOM gilt. Bei einer **ProcessingInstruction** kann es sich, gemäß der Spezifikation „Namespaces in XML“, nur um Namen ohne Doppelpunkt (NCNames) handeln, und nicht um qualifizierte Namen (QNames).

Aus Abschnitt 6 der Spezifikation „Namespaces in XML“ ergibt sich Folgendes: Wenn die **Load**-Methode und die **LoadXml**-Methode entsprechend der Spezifikation verwendet werden, hat dies in einem Dokument folgende Auswirkungen:

- Alle Elementtypen und Attributnamen enthalten entweder keinen oder einen Doppelpunkt.

- In Entitätsnamen, "ProcessingInstruction"-Zielen oder Notationsnamen ist kein Doppelpunkt enthalten.

Da `<?xml:stylesheet?>` einen Doppelpunkt enthält, verstößt der Name gegen die zweite der obigen Regeln.

Gemäß der W3C-Empfehlung [Associating Style Sheets with XML documents Version 1.0](https://www.w3.org/TR/xml-stylesheet/), lautet die Verarbeitungsanweisung zum Verknüpfen eines XSL-Stylesheets mit einem XML-Dokument `<?xml-stylesheet?>`, d.h. der Doppelpunkt wird durch einen Bindestrich ersetzt.

## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
