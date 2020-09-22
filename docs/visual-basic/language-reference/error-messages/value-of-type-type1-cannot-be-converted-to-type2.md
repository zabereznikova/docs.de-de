---
title: Der Wert vom Typ "Typ1" kann nicht zu "Typ2" konvertiert werden
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 8c80429db618e1bcadce1a58a6514d625f0b3cf1
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870232"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a><span data-ttu-id="e368b-102">Der Wert vom Typ "Typ1" kann nicht zu "Typ2" konvertiert werden</span><span class="sxs-lookup"><span data-stu-id="e368b-102">Value of type 'type1' cannot be converted to 'type2'</span></span>

<span data-ttu-id="e368b-103">Der Wert vom Typ ' Typ1 ' kann nicht in ' Typ2 ' konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="e368b-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="e368b-104">Sie können die Value-Eigenschaft verwenden, um den Zeichen folgen Wert des ersten Elements von "" zu erhalten \<parentElement> .</span><span class="sxs-lookup"><span data-stu-id="e368b-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="e368b-105">Es wurde versucht, ein XML-Literal implizit in einen bestimmten Typ umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="e368b-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="e368b-106">Das XML-Literal kann nicht implizit in den angegebenen Typ umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e368b-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="e368b-107">**Fehler-ID:** BC31194</span><span class="sxs-lookup"><span data-stu-id="e368b-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e368b-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="e368b-108">To correct this error</span></span>  
  
- <span data-ttu-id="e368b-109">Verwenden Sie die `Value` -Eigenschaft des XML-Literals, um auf dessen Wert als `String`zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="e368b-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="e368b-110">Verwenden Sie die `CType` -Funktion, eine weitere Typkonvertierungsfunktion, oder die <xref:System.Convert> -Klasse, um den Wert in den angegebenen Typ umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="e368b-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e368b-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e368b-111">See also</span></span>

- <xref:System.Convert>
- [<span data-ttu-id="e368b-112">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="e368b-112">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="e368b-113">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="e368b-113">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="e368b-114">XML</span><span class="sxs-lookup"><span data-stu-id="e368b-114">XML</span></span>](../../programming-guide/language-features/xml/index.md)
