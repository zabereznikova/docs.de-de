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
# <a name="bc30812-optional-parameters-must-specify-a-default-value"></a>BC30812: optionale Parameter müssen einen Standardwert angeben.

Optionale Parameter müssen Standardwerte bereitstellen, die verwendet werden können, wenn kein Parameter von einer aufrufenden Prozedur bereitgestellt wird.

**Fehler-ID:** BC30812

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird BC30812 generiert:

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

Geben Sie Standardwerte für optionale Parameter an:

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a>Siehe auch

- [Optional](../modifiers/optional.md)
