---
title: Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 2e57dc63cb7ad8b2e061296a082d6fa79b464f08
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592039"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="92ef0-102">Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.</span><span class="sxs-lookup"><span data-stu-id="92ef0-102">XML comment exception must have a 'cref' attribute</span></span>
<span data-ttu-id="92ef0-103">Das > Tag \<exception bietet eine Möglichkeit, die Ausnahmen zu dokumentieren, die möglicherweise von einer Methode ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="92ef0-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="92ef0-104">Das erforderliche `cref`-Attribut legt den Namen eines Members fest, der vom Dokumentations Generator geprüft wird.</span><span class="sxs-lookup"><span data-stu-id="92ef0-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="92ef0-105">Wenn der Member vorhanden ist, wird er in den kanonischen Elementnamen in der Dokumentations Datei übersetzt.</span><span class="sxs-lookup"><span data-stu-id="92ef0-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="92ef0-106">**Fehler-ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="92ef0-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="92ef0-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="92ef0-107">To correct this error</span></span>  
  
- <span data-ttu-id="92ef0-108">Fügen Sie der Ausnahme das `cref`-Attribut wie folgt hinzu:</span><span class="sxs-lookup"><span data-stu-id="92ef0-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    <span data-ttu-id="92ef0-109">xml</span><span class="sxs-lookup"><span data-stu-id="92ef0-109">xml</span></span>  
    <span data-ttu-id="92ef0-110"><exception cref="member">Beschreibung</exception> von ""</span><span class="sxs-lookup"><span data-stu-id="92ef0-110">'''<exception cref="member">description</exception></span></span>  
    ```  
  
## See also

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md)
