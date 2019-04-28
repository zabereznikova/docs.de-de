---
title: Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: a974df5d2305b88946981d0d258a8088b23d3fc3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766603"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="117be-102">Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.</span><span class="sxs-lookup"><span data-stu-id="117be-102">XML comment exception must have a 'cref' attribute</span></span>
<span data-ttu-id="117be-103">Die \<Ausnahme >-Tag bietet eine Möglichkeit, die Ausnahmen zu dokumentieren, die von einer Methode ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="117be-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="117be-104">Die erforderlichen `cref` -Attribut legt den Namen eines Members, der von der Dokumentations-Generator überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="117be-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="117be-105">Wenn das Element vorhanden ist, wird es in den kanonischen Elementnamen in der Dokumentationsdatei übersetzt.</span><span class="sxs-lookup"><span data-stu-id="117be-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="117be-106">**Fehler-ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="117be-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="117be-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="117be-107">To correct this error</span></span>  
  
- <span data-ttu-id="117be-108">Hinzufügen der `cref` -Attribut auf die Ausnahme wie folgt:</span><span class="sxs-lookup"><span data-stu-id="117be-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="117be-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="117be-109">See also</span></span>

- [<span data-ttu-id="117be-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="117be-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [<span data-ttu-id="117be-111">Vorgehensweise: Erstellen von XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="117be-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="117be-112">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="117be-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
