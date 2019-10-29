---
title: Optionale Parameter müssen einen Standardwert bestimmen.
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: eb782b2fa1fb73c7407b57a0942e5eebb30474ff
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040930"
---
# <a name="optional-parameters-must-specify-a-default-value"></a>Optionale Parameter müssen einen Standardwert bestimmen.

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
