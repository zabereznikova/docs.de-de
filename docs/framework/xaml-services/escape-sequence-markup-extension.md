---
title: '{} Escapesequenz - Markuperweiterung'
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
ms.openlocfilehash: 9f6743dd8a82891ac2233978550e5679130de0be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182069"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="ed333-102">{}-Escapesequenz/Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="ed333-102">{} Escape Sequence / Markup Extension</span></span>
<span data-ttu-id="ed333-103">Stellt die XAML-Escapesequenz für Attributwerte bereit.</span><span class="sxs-lookup"><span data-stu-id="ed333-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="ed333-104">Die-Escapesequenz kann nachfolgende Werte im Attribut als Literal interpretiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed333-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="ed333-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="ed333-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="ed333-106">Verwendung von XAML-Eigenschaftenelementen</span><span class="sxs-lookup"><span data-stu-id="ed333-106">XAML Property Element Usage</span></span>  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="ed333-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="ed333-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ed333-108">*literalValue*</span><span class="sxs-lookup"><span data-stu-id="ed333-108">*literalValue*</span></span>|<span data-ttu-id="ed333-109">Das Zeichenfolgenliteral, das die Escape-Sequenz folgt.</span><span class="sxs-lookup"><span data-stu-id="ed333-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="ed333-110">Diese Zeichenfolge enthält in der Regel eine öffnende oder schließende Klammer ({oder}).</span><span class="sxs-lookup"><span data-stu-id="ed333-110">Typically this string contains an open or close brace ({ or }).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed333-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed333-111">Remarks</span></span>  
 <span data-ttu-id="ed333-112">Die Escape-Sequenz ({}) wird verwendet, damit eine öffnende geschweifte Klammer ({}) als Literalzeichen in XAML verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ed333-112">The escape sequence ({}) is used so that an open brace ({)can be used as a literal character in XAML.</span></span>  
  
 <span data-ttu-id="ed333-113">XAML-Reader in der Regel verwenden die öffnende geschweifte Klammer ({}), um anzugeben, den Einstiegspunkt einer Markuperweiterung; allerdings überprüfen sie zuerst das nächste Zeichen aus, um festzustellen, ob es sich um eine schließende geschweifte Klammer (}) ist.</span><span class="sxs-lookup"><span data-stu-id="ed333-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="ed333-114">Nur wenn die beiden geschweiften Klammern ({}) angrenzende sind, werden sie als eine Escapesequenz betrachtet.</span><span class="sxs-lookup"><span data-stu-id="ed333-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>  
  
 <span data-ttu-id="ed333-115">Wenn die Escape-Sequenz auftritt, sollte der XAML-Reader der Rest der Zeichenfolge als Zeichenfolge verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ed333-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="ed333-116">Allerdings, wenn die Escape-Sequenz auf einen Member, die über einen Typkonverter verfügt angewendet wird, kann die Zeichenfolge Typ umgewandelt werden, wenn er von einem XAML-Writer interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="ed333-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>  
  
 <span data-ttu-id="ed333-117">Die-Escapesequenz ist es sich nicht um eine Markuperweiterung und nicht durch eine Klasse gesichert.</span><span class="sxs-lookup"><span data-stu-id="ed333-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="ed333-118">Es ist jedoch eine Konvention, die XAML-Reader (einschließlich benutzerdefinierte XAML-Reader) berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="ed333-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>  
  
 <span data-ttu-id="ed333-119">Ein Anführungszeichen (") kann nicht als eine Escapesequenz, die auf diese Weise verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ed333-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="ed333-120">Wenn Sie ein Anführungszeichen als Eigenschaftswert für eine Eigenschaft des Eigenschaftenelements festlegen müssen, verwenden Sie die Syntax und platzieren Sie die Anführungszeichen als Zeichenfolge innerhalb der Property-Element, oder Verwenden einer XML-Zeichen-Entität.</span><span class="sxs-lookup"><span data-stu-id="ed333-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="ed333-121">Für eine Inhaltseigenschaft kann das Anführungszeichen der gesamte Inhalt sein.</span><span class="sxs-lookup"><span data-stu-id="ed333-121">For a content property, the quotation mark can be the entire content.</span></span>  
  
 <span data-ttu-id="ed333-122">Die Escape-Sequenz ({}) ist häufig erforderlich, wenn einen XML-Datentyp angeben, die an einem Ort Namespacequalifizierer einschließen muss, wo eine XAML-Markuperweiterung angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ed333-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="ed333-123">Dies schließt den Start einen XAML-Attributwert, und klicken Sie in einer Markuperweiterung, sofort nach einem Gleichheitszeichen (=).</span><span class="sxs-lookup"><span data-stu-id="ed333-123">This includes the start of a XAML attribute value, and in a markup extension, immediately after an equal sign (=).</span></span> <span data-ttu-id="ed333-124">Das folgende Beispiel zeigt die Escapesequenzen für einen XML-Namespace, der am Anfang einer XAML-Attributwert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ed333-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>  
  
 [!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a><span data-ttu-id="ed333-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed333-125">See also</span></span>

- [<span data-ttu-id="ed333-126">Typkonverter und Markuperweiterungen für XAML</span><span class="sxs-lookup"><span data-stu-id="ed333-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions-for-xaml.md)
- [<span data-ttu-id="ed333-127">XML-Zeichenentitäten und XAML</span><span class="sxs-lookup"><span data-stu-id="ed333-127">XML Character Entities and XAML</span></span>](xml-character-entities-and-xaml.md)
