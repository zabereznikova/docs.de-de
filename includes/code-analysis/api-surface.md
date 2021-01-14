---
ms.openlocfilehash: bf7ea8a36b9c36d82b4c00ada890829bf4c2c024
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "97700858"
---
### <a name="include-specific-api-surfaces"></a><span data-ttu-id="786f7-101">Bestimmte API-Oberflächen einschließen</span><span class="sxs-lookup"><span data-stu-id="786f7-101">Include specific API surfaces</span></span>

<span data-ttu-id="786f7-102">Sie können basierend auf ihrer Barrierefreiheit konfigurieren, für welche Teile Ihrer Codebasis diese Regel ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="786f7-102">You can configure which parts of your codebase to run this rule on, based on their accessibility.</span></span> <span data-ttu-id="786f7-103">Um z. b. anzugeben, dass die Regel nur für die nicht öffentliche API-Oberfläche ausgeführt werden soll, fügen Sie das folgende Schlüssel-Wert-Paar in eine *Editor config* -Datei in Ihrem Projekt ein:</span><span class="sxs-lookup"><span data-stu-id="786f7-103">For example, to specify that the rule should run only against the non-public API surface, add the following key-value pair to an *.editorconfig* file in your project:</span></span>

```ini
dotnet_code_quality.CAXXXX.api_surface = private, internal
```
