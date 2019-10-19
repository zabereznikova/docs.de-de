---
title: Optionale Parameter müssen einen Standardwert bestimmen.
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 8ec4627d070cc670ce04be3a5d0298dba0a279d0
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582131"
---
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="6d5ce-102">Optionale Parameter müssen einen Standardwert bestimmen.</span><span class="sxs-lookup"><span data-stu-id="6d5ce-102">Optional parameters must specify a default value</span></span>

<span data-ttu-id="6d5ce-103">Optionale Parameter müssen Standardwerte bereitstellen, die verwendet werden können, wenn kein Parameter von einer aufrufenden Prozedur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6d5ce-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>

<span data-ttu-id="6d5ce-104">**Fehler-ID:** BC30812</span><span class="sxs-lookup"><span data-stu-id="6d5ce-104">**Error ID:** BC30812</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6d5ce-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6d5ce-105">To correct this error</span></span>

<span data-ttu-id="6d5ce-106">Geben Sie Standardwerte für optionale Parameter an. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6d5ce-106">Specify default values for optional parameters; for example:</span></span>

```vb
Sub Proc1(ByVal X As Integer,
      Optional ByVal Y As String = "Default Value")
    MsgBox("Default argument is: " & Y)
End Sub
```

## <a name="see-also"></a><span data-ttu-id="6d5ce-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d5ce-107">See also</span></span>

- [<span data-ttu-id="6d5ce-108">Optional</span><span class="sxs-lookup"><span data-stu-id="6d5ce-108">Optional</span></span>](../../../visual-basic/language-reference/modifiers/optional.md)
