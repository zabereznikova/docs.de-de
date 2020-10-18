---
title: Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 18e7aa5f6905eaa9c509aa21fe6f5bfcd54d46f0
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163297"
---
# <a name="bc42319-xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="4824a-102">BC42319: die XML-Kommentar Ausnahme muss ein "kref"-Attribut aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4824a-102">BC42319: XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="4824a-103">Das- \<exception> Tag bietet eine Möglichkeit, die Ausnahmen zu dokumentieren, die möglicherweise von einer Methode ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="4824a-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="4824a-104">Das erforderliche `cref` Attribut gibt den Namen eines Members an, der vom Dokumentations Generator geprüft wird.</span><span class="sxs-lookup"><span data-stu-id="4824a-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="4824a-105">Wenn der Member vorhanden ist, wird er in den kanonischen Elementnamen in der Dokumentations Datei übersetzt.</span><span class="sxs-lookup"><span data-stu-id="4824a-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="4824a-106">**Fehler-ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="4824a-106">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4824a-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4824a-107">To correct this error</span></span>

<span data-ttu-id="4824a-108">Fügen Sie der Ausnahme das- `cref` Attribut wie folgt hinzu:</span><span class="sxs-lookup"><span data-stu-id="4824a-108">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="4824a-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4824a-109">See also</span></span>

- [\<exception>](../xmldoc/exception.md)
- [<span data-ttu-id="4824a-110">Vorgehensweise: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="4824a-110">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="4824a-111">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="4824a-111">XML Comment Tags</span></span>](../xmldoc/index.md)
