---
title: Optionale Parameter müssen einen Standardwert bestimmen.
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 3718fe5c42c8af0948f3b5cb0d120c6876c6f98f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162452"
---
# <a name="bc30812-optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="008f1-102">BC30812: optionale Parameter müssen einen Standardwert angeben.</span><span class="sxs-lookup"><span data-stu-id="008f1-102">BC30812: Optional parameters must specify a default value</span></span>

<span data-ttu-id="008f1-103">Optionale Parameter müssen Standardwerte bereitstellen, die verwendet werden können, wenn kein Parameter von einer aufrufenden Prozedur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="008f1-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>

<span data-ttu-id="008f1-104">**Fehler-ID:** BC30812</span><span class="sxs-lookup"><span data-stu-id="008f1-104">**Error ID:** BC30812</span></span>

## <a name="example"></a><span data-ttu-id="008f1-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="008f1-105">Example</span></span>

<span data-ttu-id="008f1-106">Im folgenden Beispiel wird BC30812 generiert:</span><span class="sxs-lookup"><span data-stu-id="008f1-106">The following example generates BC30812:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a><span data-ttu-id="008f1-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="008f1-107">To correct this error</span></span>

<span data-ttu-id="008f1-108">Geben Sie Standardwerte für optionale Parameter an:</span><span class="sxs-lookup"><span data-stu-id="008f1-108">Specify default values for optional parameters:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a><span data-ttu-id="008f1-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="008f1-109">See also</span></span>

- [<span data-ttu-id="008f1-110">Optional</span><span class="sxs-lookup"><span data-stu-id="008f1-110">Optional</span></span>](../modifiers/optional.md)
