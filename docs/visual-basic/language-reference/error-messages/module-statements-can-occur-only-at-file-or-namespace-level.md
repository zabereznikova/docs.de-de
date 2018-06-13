---
title: '&#39;Modul&#39; Anweisungen können nur auf Namespace- oder Dateiebene verwendet werden'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 53199c2d7081445dc5490d5c54c98f93ee7522eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593164"
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="ee16b-102">&#39;Modul&#39; Anweisungen können nur auf Namespace- oder Dateiebene verwendet werden</span><span class="sxs-lookup"><span data-stu-id="ee16b-102">&#39;Module&#39; statements can occur only at file or namespace level</span></span>
<span data-ttu-id="ee16b-103">`Module` -Anweisungen müssen am Anfang der Quelldatei angezeigt werden unmittelbar nach `Option` und `Imports` -Anweisungen und globale Attribute Namespacedeklarationen, aber vor allen anderen Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="ee16b-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="ee16b-104">**Fehler-ID:** BC30617</span><span class="sxs-lookup"><span data-stu-id="ee16b-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ee16b-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ee16b-105">To correct this error</span></span>  
  
-   <span data-ttu-id="ee16b-106">Verschieben der `Module` Anweisungen am Anfang der Namespacedeklaration oder Quelldatei Datei Namespace.</span><span class="sxs-lookup"><span data-stu-id="ee16b-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee16b-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee16b-107">See Also</span></span>  
 [<span data-ttu-id="ee16b-108">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ee16b-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
