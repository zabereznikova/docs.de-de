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
# <a name="style-sheet-directives-embedded-in-a-document"></a><span data-ttu-id="6238e-102">In ein Dokument eingebettete Stylesheetdirektiven</span><span class="sxs-lookup"><span data-stu-id="6238e-102">Style Sheet Directives Embedded in a Document</span></span>

<span data-ttu-id="6238e-103">Gelegentlich enthält vorhandener XML-Code die Stylesheetanweisung `<?xml:stylesheet?>`.</span><span class="sxs-lookup"><span data-stu-id="6238e-103">Occasionally, existing XML contains the style sheet directive of `<?xml:stylesheet?>`.</span></span> <span data-ttu-id="6238e-104">Microsoft Internet Explorer akzeptiert diese als Alternative zur `<?xml-stylesheet?>`-Syntax.</span><span class="sxs-lookup"><span data-stu-id="6238e-104">Microsoft Internet Explorer accepts this as an alternative to the `<?xml-stylesheet?>` syntax.</span></span> <span data-ttu-id="6238e-105">Wenn die XML-Daten, wie im Folgenden dargestellt, eine `<?xml:stylesheet?>`-Anweisung enthalten, wird durch den Versuch, diese Daten in das Dokumentobjektmodell (DOM) zu laden, eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6238e-105">When the XML data contains an `<?xml:stylesheet?>` directive, as shown in the following data, attempting to load this data into the XML Document Object Model (DOM) throws an exception.</span></span>

```xml
<?xml version="1.0" ?>
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>
<root>
    <test>Node 1</test>
    <test>Node 2</test>
</root>
```

<span data-ttu-id="6238e-106">Der Grund hierfür ist, dass `<?xml:stylesheet?>` als ungültige **ProcessingInstruction** für das DOM gilt.</span><span class="sxs-lookup"><span data-stu-id="6238e-106">This occurs because the `<?xml:stylesheet?>` is considered an invalid **ProcessingInstruction** to the DOM.</span></span> <span data-ttu-id="6238e-107">Bei einer **ProcessingInstruction** kann es sich, gemäß der Spezifikation „Namespaces in XML“, nur um Namen ohne Doppelpunkt (NCNames) handeln, und nicht um qualifizierte Namen (QNames).</span><span class="sxs-lookup"><span data-stu-id="6238e-107">Any **ProcessingInstruction**, according to the Namespaces in XML specification, can only be no-colon names (NCNames), as opposed to qualified names (QNames).</span></span>

<span data-ttu-id="6238e-108">Aus Abschnitt 6 der Spezifikation „Namespaces in XML“ ergibt sich Folgendes: Wenn die **Load**-Methode und die **LoadXml**-Methode entsprechend der Spezifikation verwendet werden, hat dies in einem Dokument folgende Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="6238e-108">From Section 6 of the Namespaces in XML specification, the effect of having the **Load** and **LoadXml** methods conform to the specification is that in a document:</span></span>

- <span data-ttu-id="6238e-109">Alle Elementtypen und Attributnamen enthalten entweder keinen oder einen Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="6238e-109">All element types and attribute names contain either zero or one colon.</span></span>

- <span data-ttu-id="6238e-110">In Entitätsnamen, "ProcessingInstruction"-Zielen oder Notationsnamen ist kein Doppelpunkt enthalten.</span><span class="sxs-lookup"><span data-stu-id="6238e-110">No entity names, ProcessingInstruction targets, or notation names contain any colons.</span></span>

<span data-ttu-id="6238e-111">Da `<?xml:stylesheet?>` einen Doppelpunkt enthält, verstößt der Name gegen die zweite der obigen Regeln.</span><span class="sxs-lookup"><span data-stu-id="6238e-111">With the `<?xml:stylesheet?>` containing a colon, you now violate the rule in the second bullet.</span></span>

<span data-ttu-id="6238e-112">Gemäß der W3C-Empfehlung [Associating Style Sheets with XML documents Version 1.0](https://www.w3.org/TR/xml-stylesheet/), lautet die Verarbeitungsanweisung zum Verknüpfen eines XSL-Stylesheets mit einem XML-Dokument `<?xml-stylesheet?>`, d.h. der Doppelpunkt wird durch einen Bindestrich ersetzt.</span><span class="sxs-lookup"><span data-stu-id="6238e-112">According to the World Wide Web Consortium (W3C) [Associating Style Sheets with XML documents Version 1.0 Recommendation](https://www.w3.org/TR/xml-stylesheet/),  the processing instruction to associate an XSLT style sheet with an XML document is `<?xml-stylesheet?>`, with a dash replacing the colon.</span></span>

## <a name="see-also"></a><span data-ttu-id="6238e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6238e-113">See also</span></span>

- [<span data-ttu-id="6238e-114">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="6238e-114">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
