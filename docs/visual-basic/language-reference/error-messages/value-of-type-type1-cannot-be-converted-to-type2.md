---
title: Der Wert vom Typ "Typ1" kann nicht zu "Typ2" konvertiert werden
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: c8480c6fab2bff931950ebc21d0a8affe3c41c66
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774815"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a><span data-ttu-id="72017-102">Der Wert vom Typ "Typ1" kann nicht zu "Typ2" konvertiert werden</span><span class="sxs-lookup"><span data-stu-id="72017-102">Value of type 'type1' cannot be converted to 'type2'</span></span>
<span data-ttu-id="72017-103">Wert vom Typ "Typ1" kann nicht in 'Typ2' konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="72017-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="72017-104">Sie können die Value-Eigenschaft den Zeichenfolgenwert des ersten Elements der abzurufenden "\<ParentElement >'.</span><span class="sxs-lookup"><span data-stu-id="72017-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="72017-105">Es wurde versucht, ein XML-Literal implizit in einen bestimmten Typ umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="72017-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="72017-106">Das XML-Literal kann nicht implizit in den angegebenen Typ umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="72017-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="72017-107">**Fehler-ID:** BC31194</span><span class="sxs-lookup"><span data-stu-id="72017-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="72017-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="72017-108">To correct this error</span></span>  
  
- <span data-ttu-id="72017-109">Verwenden Sie die `Value` -Eigenschaft des XML-Literals, um auf dessen Wert als `String`zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="72017-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="72017-110">Verwenden Sie die `CType` -Funktion, eine weitere Typkonvertierungsfunktion, oder die <xref:System.Convert> -Klasse, um den Wert in den angegebenen Typ umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="72017-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72017-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72017-111">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="72017-112">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="72017-112">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="72017-113">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="72017-113">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="72017-114">XML</span><span class="sxs-lookup"><span data-stu-id="72017-114">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
