---
title: Alle Feldbreiten (außer beim letzten Element) müssen größer als 0 (null) sein.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: 4fb40e5f2b458fbbd0bfdb329f75250e70fd7e28
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083916"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a><span data-ttu-id="9736e-102">Alle Feldbreiten (außer beim letzten Element) müssen größer als 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="9736e-102">All field widths, except the last element, must be greater than zero</span></span>

<span data-ttu-id="9736e-103">Alle Feldbreiten (außer beim letzten Element) müssen größer als 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="9736e-103">All field widths, except the last element, must be greater than zero.</span></span> <span data-ttu-id="9736e-104">Ein Feld mit einer Breite unter oder gleich 0 (null) im letzten Element bedeutet, dass die Länge des letzten Felds variabel ist.</span><span class="sxs-lookup"><span data-stu-id="9736e-104">A field width less than or equal to zero in the last element indicates the last field is of variable length.</span></span>  
  
 <span data-ttu-id="9736e-105">Der Vorgang ist fehlgeschlagen, da die Feldbreite eines anderen Elements, das nicht das letzte Element ist, auf 0 (null) oder kleiner festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9736e-105">The operation has failed because a field width other than the last element is set to zero or less.</span></span> <span data-ttu-id="9736e-106">Eine Feldbreite, die kleiner oder gleich 0 (null) ist, kann als letztes Element verwendet werden, um anzugeben, dass dass die Länge des letzten Felds variabel ist. Sie kann jedoch nicht als ein anderes Element verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9736e-106">A field width less than or equal to zero can be used as the last element to indicate that the last field is of variable length, but it cannot be used as any other element.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9736e-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9736e-107">To correct this error</span></span>  
  
- <span data-ttu-id="9736e-108">Legen Sie die Feldbreite auf die richtige Länge fest.</span><span class="sxs-lookup"><span data-stu-id="9736e-108">Set the field width to the correct length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9736e-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9736e-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>
- [<span data-ttu-id="9736e-110">Vorgehensweise: Lesen aus Textdateien mit fester Breite</span><span class="sxs-lookup"><span data-stu-id="9736e-110">How to: Read From Fixed-width Text Files</span></span>](../developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="9736e-111">TextFieldParser Object</span><span class="sxs-lookup"><span data-stu-id="9736e-111">TextFieldParser Object</span></span>](../language-reference/objects/textfieldparser-object.md)
