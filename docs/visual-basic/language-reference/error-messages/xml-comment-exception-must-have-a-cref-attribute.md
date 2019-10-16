---
title: Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 54965f3796b6c5ef0e387cd354abcb5740476257
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321172"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="15977-102">Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.</span><span class="sxs-lookup"><span data-stu-id="15977-102">XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="15977-103">Das > Tag \<exception bietet eine Möglichkeit, die Ausnahmen zu dokumentieren, die möglicherweise von einer Methode ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="15977-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="15977-104">Das erforderliche `cref`-Attribut legt den Namen eines Members fest, der vom Dokumentations Generator geprüft wird.</span><span class="sxs-lookup"><span data-stu-id="15977-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="15977-105">Wenn der Member vorhanden ist, wird er in den kanonischen Elementnamen in der Dokumentations Datei übersetzt.</span><span class="sxs-lookup"><span data-stu-id="15977-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="15977-106">**Fehler-ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="15977-106">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="15977-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="15977-107">To correct this error</span></span>

<span data-ttu-id="15977-108">Fügen Sie der Ausnahme das `cref`-Attribut wie folgt hinzu:</span><span class="sxs-lookup"><span data-stu-id="15977-108">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="15977-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15977-109">See also</span></span>

- [<span data-ttu-id="15977-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="15977-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [<span data-ttu-id="15977-111">Gewusst wie: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="15977-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="15977-112">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="15977-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
