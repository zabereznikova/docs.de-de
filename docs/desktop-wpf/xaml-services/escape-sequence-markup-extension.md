---
title: '{}Escape Sequence - Markup-Erweiterung'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432965"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="699a2-102">{}Escape-Sequenz / Markup-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="699a2-102">{} Escape sequence / markup extension</span></span>

<span data-ttu-id="699a2-103">Stellt die XAML-Escapesequenz für Attributwerte bereit.</span><span class="sxs-lookup"><span data-stu-id="699a2-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="699a2-104">Die Escapesequenz ermöglicht es, die nachfolgenden Werte im Attribut als Literal zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="699a2-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="699a2-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="699a2-105">XAML Attribute Usage</span></span>

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a><span data-ttu-id="699a2-106">Verwendung von XAML-Eigenschaftenelementen</span><span class="sxs-lookup"><span data-stu-id="699a2-106">XAML Property Element Usage</span></span>

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="699a2-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="699a2-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="699a2-108">*literalValue*</span><span class="sxs-lookup"><span data-stu-id="699a2-108">*literalValue*</span></span>|<span data-ttu-id="699a2-109">Die Literalzeichenfolge, die der Escapesequenz folgt.</span><span class="sxs-lookup"><span data-stu-id="699a2-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="699a2-110">In der Regel enthält diese Zeichenfolge eine offene oder schließende geschweifte Klammer (- oder .</span><span class="sxs-lookup"><span data-stu-id="699a2-110">Typically this string contains an open or close brace ({ or }).</span></span>|

## <a name="remarks"></a><span data-ttu-id="699a2-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="699a2-111">Remarks</span></span>

<span data-ttu-id="699a2-112">Die Escapesequenz{}( ) wird verwendet, damit eine offene geschweifte Klammer als Literalzeichen in XAML verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="699a2-112">The escape sequence ({}) is used so that an open brace ({) can be used as a literal character in XAML.</span></span>

<span data-ttu-id="699a2-113">XAML-Reader verwenden in der Regel die offene geschweifte Klammer , um den Einstiegspunkt einer Markuperweiterung zu bezeichnen; sie überprüfen jedoch zuerst das nächste Zeichen, um festzustellen, ob es sich um eine schließende geschweifte Klammer handelt.</span><span class="sxs-lookup"><span data-stu-id="699a2-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="699a2-114">Nur wenn die beiden{}geschweiften Klammern ( ) nebeneinander liegen, werden sie als Escapesequenz betrachtet.</span><span class="sxs-lookup"><span data-stu-id="699a2-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>

<span data-ttu-id="699a2-115">Wenn die Escapesequenz gefunden wird, sollte der XAML-Reader den Rest der Zeichenfolge als Zeichenfolge verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="699a2-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="699a2-116">Wenn die Escapesequenz jedoch auf ein Element angewendet wird, das über einen Typkonverter verfügt, wird die Zeichenfolge möglicherweise typkonvertieren, wenn sie von einem XAML-Writer interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="699a2-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>

<span data-ttu-id="699a2-117">Die Escapesequenz ist keine Markuperweiterung und wird nicht von einer Klasse unterstützt.</span><span class="sxs-lookup"><span data-stu-id="699a2-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="699a2-118">Es handelt sich jedoch um eine Konvention, die XAML-Reader (einschließlich benutzerdefinierter XAML-Reader) beachten sollten.</span><span class="sxs-lookup"><span data-stu-id="699a2-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>

<span data-ttu-id="699a2-119">Ein Anführungszeichen (") kann auf diese Weise nicht als Escapesequenz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="699a2-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="699a2-120">Wenn Sie ein Anführungszeichen als Eigenschaftswert für eine Eigenschaftseigenschaft festlegen müssen, verwenden Sie die Eigenschaftenelementsyntax, und platzieren Sie das Anführungszeichen als Zeichenfolge innerhalb des Eigenschaftselements, oder verwenden Sie eine XML-Zeichenentität.</span><span class="sxs-lookup"><span data-stu-id="699a2-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="699a2-121">Bei einer Content-Eigenschaft kann das Anführungszeichen der gesamte Inhalt sein.</span><span class="sxs-lookup"><span data-stu-id="699a2-121">For a content property, the quotation mark can be the entire content.</span></span>

<span data-ttu-id="699a2-122">Die Escapesequenz{}( ) ist häufig erforderlich, wenn ein XML-Typ angegeben wird, der einen Namespacequalifizierer an einem Speicherort enthalten muss, an dem eine XAML-Markuperweiterung angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="699a2-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="699a2-123">Dieser Speicherort enthält den Start eines XAML-Attributwerts und in einer Markuperweiterung unmittelbar nach einem Gleichheitszeichen (=).</span><span class="sxs-lookup"><span data-stu-id="699a2-123">This location includes the start of a XAML attribute value, and in a markup extension immediately after an equal sign (=).</span></span> <span data-ttu-id="699a2-124">Das folgende Beispiel zeigt Escapesequenzen für einen XML-Namespace, der am Anfang eines XAML-Attributwerts angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="699a2-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a><span data-ttu-id="699a2-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="699a2-125">See also</span></span>

- [<span data-ttu-id="699a2-126">Typkonverter und Markuperweiterungen für XAML</span><span class="sxs-lookup"><span data-stu-id="699a2-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions.md)
- [<span data-ttu-id="699a2-127">XML-Zeichenentitäten und XAML</span><span class="sxs-lookup"><span data-stu-id="699a2-127">XML Character Entities and XAML</span></span>](xml-character-entities.md)
