---
title: '{}-Escapesequenz - Markuperweiterung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8419a1e89d5e94b9868b0fd1fb81540253efca5d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="60e2b-102">{}-Escapesequenz/Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="60e2b-102">{} Escape Sequence / Markup Extension</span></span>
<span data-ttu-id="60e2b-103">Stellt die Verwendung von XAML-Escapesequenz für Attributwerte bereit.</span><span class="sxs-lookup"><span data-stu-id="60e2b-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="60e2b-104">Die-Escapesequenz kann nachfolgende Werte im Attribut als Literal interpretiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="60e2b-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="60e2b-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="60e2b-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="60e2b-106">Verwendung von XAML-Eigenschaftenelementen</span><span class="sxs-lookup"><span data-stu-id="60e2b-106">XAML Property Element Usage</span></span>  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="60e2b-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="60e2b-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60e2b-108">*literalValue*</span><span class="sxs-lookup"><span data-stu-id="60e2b-108">*literalValue*</span></span>|<span data-ttu-id="60e2b-109">Das Zeichenfolgenliteral, das die-Escapesequenz folgt.</span><span class="sxs-lookup"><span data-stu-id="60e2b-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="60e2b-110">Diese Zeichenfolge enthält in der Regel eine öffnende oder schließende Klammer ({oder}).</span><span class="sxs-lookup"><span data-stu-id="60e2b-110">Typically this string contains an open or close brace ({ or }).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60e2b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60e2b-111">Remarks</span></span>  
 <span data-ttu-id="60e2b-112">Die Escapesequenz ({}) wird verwendet, sodass eine öffnende geschweifte Klammer ({}) als Literalzeichen in XAML verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="60e2b-112">The escape sequence ({}) is used so that an open brace ({)can be used as a literal character in XAML.</span></span>  
  
 <span data-ttu-id="60e2b-113">XAML-Readern in der Regel verwenden die öffnende geschweifte Klammer ({}), um den Einstiegspunkt einer Markuperweiterung zu kennzeichnen; allerdings überprüfen sie zunächst das nächste Zeichen aus, um festzustellen, ob es sich um eine schließende geschweifte Klammer (}) ist.</span><span class="sxs-lookup"><span data-stu-id="60e2b-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="60e2b-114">Nur, wenn die beiden geschweiften Klammern ({}) nebeneinander angeordnet sind, werden sie eine Escapesequenz angesehen.</span><span class="sxs-lookup"><span data-stu-id="60e2b-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>  
  
 <span data-ttu-id="60e2b-115">Wenn die-Escapesequenz gefunden wird, sollte der XAML-Reader die restliche Zeichenfolge als Zeichenfolge verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="60e2b-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="60e2b-116">Jedoch wenn Escape-Zeichenfolge auf ein Element angewendet wird, einen Typkonverter hat, kann die Zeichenfolge Konvertierung vom Typ unterzogen werden, wenn er von einem XAML-Writer interpretiert wird.</span><span class="sxs-lookup"><span data-stu-id="60e2b-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>  
  
 <span data-ttu-id="60e2b-117">Die-Escapesequenz ist eine Markuperweiterung und nicht durch eine Klasse unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="60e2b-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="60e2b-118">Es ist jedoch eine Konvention, die XAML-Reader (einschließlich benutzerdefinierter XAML-Reader) berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="60e2b-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>  
  
 <span data-ttu-id="60e2b-119">Ein Anführungszeichen (") kann nicht als Escapesequenz auf diese Weise verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="60e2b-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="60e2b-120">Wenn Sie ein Anführungszeichen als einen Eigenschaftswert für eine Eigenschaft des Eigenschaftenelements festlegen müssen, verwenden Sie Eigenschaftenelementsyntax und platzieren Sie die Anführungszeichen als Zeichenfolge innerhalb der Property-Element, oder eine XML-Zeichen-Entität.</span><span class="sxs-lookup"><span data-stu-id="60e2b-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="60e2b-121">Für einen Content-Eigenschaft kann das Anführungszeichen der gesamte Inhalt sein.</span><span class="sxs-lookup"><span data-stu-id="60e2b-121">For a content property, the quotation mark can be the entire content.</span></span>  
  
 <span data-ttu-id="60e2b-122">Die Escapesequenz ({}) ist häufig erforderlich, wenn Sie einen XML-Datentyp angeben, der einen Namespacequalifizierer an einem Ort einschließen muss, in dem dargestellt wird, eine XAML-Markuperweiterung.</span><span class="sxs-lookup"><span data-stu-id="60e2b-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="60e2b-123">Dies schließt den Beginn des XAML-Attributwert und in eine Markuperweiterung, sofort nach einem Gleichheitszeichen (=).</span><span class="sxs-lookup"><span data-stu-id="60e2b-123">This includes the start of a XAML attribute value, and in a markup extension, immediately after an equal sign (=).</span></span> <span data-ttu-id="60e2b-124">Das folgende Beispiel zeigt die Escapesequenzen für einen XML-Namespace, der am Anfang des XAML-Attributwert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="60e2b-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>  
  
 [!code-xaml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a><span data-ttu-id="60e2b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60e2b-125">See Also</span></span>  
 [<span data-ttu-id="60e2b-126">Typkonverter und Markuperweiterungen für XAML</span><span class="sxs-lookup"><span data-stu-id="60e2b-126">Type Converters and Markup Extensions for XAML</span></span>](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)  
 [<span data-ttu-id="60e2b-127">XML-Zeichenentitäten und XAML</span><span class="sxs-lookup"><span data-stu-id="60e2b-127">XML Character Entities and XAML</span></span>](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)
