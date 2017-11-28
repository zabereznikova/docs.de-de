---
title: "Eine XML-Kommentarausnahme benötigen eine &#39; Cref &#39; Attribut"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords: BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0c22c9cd9415faf17d027c3751d166662a92b50
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a><span data-ttu-id="dfe95-102">Eine XML-Kommentarausnahme benötigen eine &#39; Cref &#39; Attribut</span><span class="sxs-lookup"><span data-stu-id="dfe95-102">XML comment exception must have a &#39;cref&#39; attribute</span></span>
<span data-ttu-id="dfe95-103">Die \<Ausnahme >-Tag bietet eine Möglichkeit, dokumentieren Sie die Ausnahmen, die von einer Methode ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="dfe95-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="dfe95-104">Die erforderliche `cref` -Attribut legt den Namen eines Members, der von der Dokumentations-Generator aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dfe95-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="dfe95-105">Wenn das Element vorhanden ist, wird er in den kanonischen Namen in der Dokumentationsdatei übersetzt.</span><span class="sxs-lookup"><span data-stu-id="dfe95-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="dfe95-106">**Fehler-ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="dfe95-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dfe95-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="dfe95-107">To correct this error</span></span>  
  
-   <span data-ttu-id="dfe95-108">Hinzufügen der `cref` -Attribut auf die Ausnahme folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="dfe95-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dfe95-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfe95-109">See Also</span></span>  
 [<span data-ttu-id="dfe95-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="dfe95-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [<span data-ttu-id="dfe95-111">Gewusst wie: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="dfe95-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [<span data-ttu-id="dfe95-112">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="dfe95-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
