---
title: Module-Anweisungen können nur auf Namespace- oder Dateiebene verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: d01c30571fc34e142300ac8706c56d5e99175fcf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397206"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="fa040-102">Module-Anweisungen können nur auf Namespace- oder Dateiebene verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fa040-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="fa040-103">`Module`-Anweisungen müssen am Anfang der Quelldatei unmittelbar nach den `Option` -und- `Imports` Anweisungen, globalen Attributen und Namespace Deklarationen, aber vor allen anderen Deklarationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fa040-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="fa040-104">**Fehler-ID:** BC30617</span><span class="sxs-lookup"><span data-stu-id="fa040-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fa040-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fa040-105">To correct this error</span></span>  
  
- <span data-ttu-id="fa040-106">Verschieben Sie die `Module` -Anweisung an den Anfang der Namespacedeklaration oder Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="fa040-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa040-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa040-107">See also</span></span>

- [<span data-ttu-id="fa040-108">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fa040-108">Module Statement</span></span>](../statements/module-statement.md)
