---
title: Objektvariablen
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: a5e61f9308d3484dc228a7d09cc2fd30a2f41b35
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410334"
---
# <a name="object-variables-in-visual-basic"></a>Objektvariablen in Visual Basic

Neben der direkten Speicherung von Werten kann eine Variable auf ein Objekt verweisen. Sie weisen einer Variablen ein Objekt zu, wenn Sie einer Variablen einen beliebigen Wert zuweisen:

- Ein Variablenname ist oft kürzer und leichter zu merken als der vollständige Pfad von Methoden und Eigenschaften, die für den Zugriff auf das Objekt selbst erforderlich sind.

- Die Verwendung einer Variablen, die auf ein Objekt verweist, ist effizienter als das wiederholte zugreifen auf das Objekt selbst über die erforderlichen Methoden oder Eigenschaften.

- Sie können eine Variable ändern, um auf andere Objekte zu verweisen, während der Code ausgeführt wird.

## <a name="making-code-shorter"></a>Code kürzerer Code

Sie können Objektvariablen verwenden, um den Code zu kürzen, den Sie eingeben müssen. Im folgenden Beispiel wird der vollständige Pfad von Methoden und Eigenschaften verwendet, um auf ein- <xref:System.Windows.Forms.Control> Objekt zuzugreifen.

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

Sie können diesen Code verkürzen und die Ausführung beschleunigen, wenn Sie eine Objekt Variable für das Steuerelement verwenden. Sie sollten die Objekt Variable mit der bestimmten Klasse deklarieren, die Sie Ihr zuweisen möchten ( `Control` in diesem Fall). Nachdem Sie der Variablen ein Objekt zugewiesen haben, können Sie es genauso behandeln wie das Objekt, auf das es verweist. Sie können die Eigenschaften des Objekts festlegen oder Abrufen oder eine der zugehörigen Methoden verwenden. Im folgenden Beispiel wird eine Objekt Variable verwendet, um den Code im vorherigen Beispiel zu vereinfachen.

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a>Weitere Informationen

- [Variablen Deklaration](variable-declaration.md)
- [Vorgehensweise: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad](how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [Deklaration von Objektvariablen](object-variable-declaration.md)
- [Zuweisung von Objektvariablen](object-variable-assignment.md)
- [Werte von Objektvariablen](object-variable-values.md)
