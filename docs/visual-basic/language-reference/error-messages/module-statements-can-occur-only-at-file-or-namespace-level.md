---
title: Module-Anweisungen können nur auf Namespace- oder Dateiebene verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: b946a527d3de3a030ac03691c77afcf440f518ee
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160313"
---
# <a name="bc30617-module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="d9428-102">BC30617: "Module"-Anweisungen können nur auf Datei-oder Namespace Ebene auftreten.</span><span class="sxs-lookup"><span data-stu-id="d9428-102">BC30617: 'Module' statements can occur only at file or namespace level</span></span>

<span data-ttu-id="d9428-103">`Module` -Anweisungen müssen am Anfang der Quelldatei unmittelbar nach den `Option` -und- `Imports` Anweisungen, globalen Attributen und Namespace Deklarationen, aber vor allen anderen Deklarationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d9428-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>

 <span data-ttu-id="d9428-104">**Fehler-ID:** BC30617</span><span class="sxs-lookup"><span data-stu-id="d9428-104">**Error ID:** BC30617</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d9428-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d9428-105">To correct this error</span></span>

- <span data-ttu-id="d9428-106">Verschieben Sie die `Module` -Anweisung an den Anfang der Namespacedeklaration oder Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="d9428-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9428-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9428-107">See also</span></span>

- [<span data-ttu-id="d9428-108">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d9428-108">Module Statement</span></span>](../statements/module-statement.md)
