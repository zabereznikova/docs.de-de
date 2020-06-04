---
title: Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: c498675ab6ae616fb63d3d76ef60bcac7e247145
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406507"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="47c23-102">Eine XML-Kommentarausnahme muss ein cref-Attribut aufweisen.</span><span class="sxs-lookup"><span data-stu-id="47c23-102">XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="47c23-103">Das- \<exception> Tag bietet eine Möglichkeit, die Ausnahmen zu dokumentieren, die möglicherweise von einer Methode ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="47c23-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="47c23-104">Das erforderliche `cref` Attribut gibt den Namen eines Members an, der vom Dokumentations Generator geprüft wird.</span><span class="sxs-lookup"><span data-stu-id="47c23-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="47c23-105">Wenn der Member vorhanden ist, wird er in den kanonischen Elementnamen in der Dokumentations Datei übersetzt.</span><span class="sxs-lookup"><span data-stu-id="47c23-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="47c23-106">**Fehler-ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="47c23-106">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="47c23-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="47c23-107">To correct this error</span></span>

<span data-ttu-id="47c23-108">Fügen Sie der Ausnahme das- `cref` Attribut wie folgt hinzu:</span><span class="sxs-lookup"><span data-stu-id="47c23-108">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="47c23-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="47c23-109">See also</span></span>

- [\<exception>](../xmldoc/exception.md)
- [<span data-ttu-id="47c23-110">Vorgehensweise: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="47c23-110">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="47c23-111">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="47c23-111">XML Comment Tags</span></span>](../xmldoc/index.md)
