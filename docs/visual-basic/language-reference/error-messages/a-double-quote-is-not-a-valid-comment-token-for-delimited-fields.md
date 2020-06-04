---
title: Doppelte Anführungszeichen sind kein gültiges Kommentartoken für Felder mit Trennzeichen, bei denen HasFieldsEnclosedInQuotes auf "True" festgelegt ist.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_InvalidComment
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
ms.openlocfilehash: a66d43d249a12ffa552073866f2e0a1e6d453608
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409938"
---
# <a name="a-double-quote-is-not-a-valid-comment-token-for-delimited-fields-where-escapequote-is-set-to-true"></a><span data-ttu-id="ed768-102">Doppelte Anführungszeichen sind kein gültiges Kommentartoken für Felder mit Trennzeichen, bei denen HasFieldsEnclosedInQuotes auf "True" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ed768-102">A double quote is not a valid comment token for delimited fields where EscapeQuote is set to True</span></span>

<span data-ttu-id="ed768-103">Als Trennzeichen für den `TextFieldParser`wurde ein Anführungszeichen angegeben, aber `EscapeQuotes` ist auf `True`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ed768-103">A quotation mark has been supplied as the delimiter for the `TextFieldParser`, but `EscapeQuotes` is set to `True`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed768-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ed768-104">To correct this error</span></span>  
  
- <span data-ttu-id="ed768-105">Legen Sie `EscapeQuotes` auf `False` fest.</span><span class="sxs-lookup"><span data-stu-id="ed768-105">Set `EscapeQuotes` to `False`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed768-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed768-106">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- [<span data-ttu-id="ed768-107">Vorgehensweise: Lesen aus durch Trennzeichen getrennten Textdateien</span><span class="sxs-lookup"><span data-stu-id="ed768-107">How to: Read From Comma-Delimited Text Files</span></span>](../../developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
