---
title: Der Wert vom Typ "Typ1" kann nicht zu "Typ2" konvertiert werden
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 4a0f3eb2b1603899e9acc1273c023ec5d0ed3132
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913346"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a><span data-ttu-id="246f9-102">Der Wert vom Typ "Typ1" kann nicht zu "Typ2" konvertiert werden</span><span class="sxs-lookup"><span data-stu-id="246f9-102">Value of type 'type1' cannot be converted to 'type2'</span></span>
<span data-ttu-id="246f9-103">Wert vom Typ "Typ1" kann nicht in 'Typ2' konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="246f9-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="246f9-104">Sie können die Value-Eigenschaft den Zeichenfolgenwert des ersten Elements der abzurufenden "\<ParentElement >'.</span><span class="sxs-lookup"><span data-stu-id="246f9-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="246f9-105">Es wurde versucht, ein XML-Literal implizit in einen bestimmten Typ umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="246f9-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="246f9-106">Das XML-Literal kann nicht implizit in den angegebenen Typ umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="246f9-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="246f9-107">**Fehler-ID:** BC31194</span><span class="sxs-lookup"><span data-stu-id="246f9-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="246f9-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="246f9-108">To correct this error</span></span>  
  
- <span data-ttu-id="246f9-109">Verwenden Sie die `Value` -Eigenschaft des XML-Literals, um auf dessen Wert als `String`zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="246f9-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="246f9-110">Verwenden Sie die `CType` -Funktion, eine weitere Typkonvertierungsfunktion, oder die <xref:System.Convert> -Klasse, um den Wert in den angegebenen Typ umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="246f9-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="246f9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="246f9-111">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="246f9-112">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="246f9-112">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="246f9-113">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="246f9-113">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="246f9-114">XML</span><span class="sxs-lookup"><span data-stu-id="246f9-114">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
