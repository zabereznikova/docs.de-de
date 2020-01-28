---
title: Formular Größe ändern
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- resizing Windows Forms
- Windows Forms, resizing
ms.assetid: 5d9dd47e-e68c-48c9-a0a3-a9ff34ba009d
ms.openlocfilehash: 8d4ce46ada505f952fc3090d10c5d893338d19f2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739306"
---
# <a name="how-to-resize-windows-forms"></a>Gewusst wie: Ändern der Größe von Windows Forms

Sie können die Größe eines Windows Forms auf verschiedene Weise angeben. Sie können die Höhe und Breite des Formulars programmgesteuert ändern, indem Sie einen neuen Wert für die <xref:System.Windows.Forms.Form.Size%2A>-Eigenschaft festlegen oder die <xref:System.Windows.Forms.Control.Height%2A>- oder die <xref:System.Windows.Forms.Control.Width%2A>-Eigenschaft einzeln anpassen. Wenn Sie Visual Studio verwenden, können Sie die Größe mithilfe der Windows Forms-Designer ändern. Siehe auch Gewusst [wie: Ändern der Größe Windows Forms mithilfe des Designers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100)).

## <a name="resize-a-form-programmatically"></a>Ändern der Größe eines Formulars Programm gesteuert

Sie können die Größe eines Formulars zur Laufzeit definieren, indem Sie die <xref:System.Windows.Forms.Form.Size%2A>-Eigenschaft des Formulars festlegen.

Im folgenden Codebeispiel wird die Formulargröße auf 100 x 100 Pixel festgelegt.

```vb
Form1.Size = New System.Drawing.Size(100, 100)
```

```csharp
Form1.Size = new System.Drawing.Size(100, 100);
```

```cpp
Form1->Size = System::Drawing::Size(100, 100);
```

## <a name="change-form-width-and-height-programmatically"></a>Programm gesteuertes Ändern der Formular Breite und-Höhe

Nachdem <xref:System.Windows.Forms.Form.Size%2A> definiert ist, ändern Sie entweder die Formularhöhe oder -breite über die <xref:System.Windows.Forms.Control.Width%2A>- oder die <xref:System.Windows.Forms.Control.Height%2A>-Eigenschaft.

Im folgenden Codebeispiel wird die Breite des Formulars ab dem linken Formularrand auf 300 Pixel festgelegt, während die Höhe konstant bleibt.

```vb
Form1.Width = 300
```

```csharp
Form1.Width = 300;
```

```cpp
Form1->Width = 300;
```

\- oder -

Ändern Sie <xref:System.Drawing.Size.Width%2A> oder <xref:System.Drawing.Size.Height%2A>, indem Sie die <xref:System.Windows.Forms.Form.Size%2A>-Eigenschaft festlegen.

Wie Sie jedoch dem folgenden Codebeispiel entnehmen können, ist diese Vorgehensweise komplizierter als das Festlegen der <xref:System.Windows.Forms.Control.Width%2A>- oder der <xref:System.Windows.Forms.Control.Height%2A>-Eigenschaft.

```vb
Form1.Size = New Size(300, Form1.Size.Height)
```

```csharp
Form1.Size = new Size(300, Form1.Size.Height);
```

```cpp
Form1->Size = System::Drawing::Size(300, Form1->Size.Height);
```

## <a name="change-form-size-by-increments-programmatically"></a>Programm gesteuertes Ändern der Formular Größe in Inkrementen

Um das Formular zu vergrößern, legen Sie die <xref:System.Drawing.Size.Width%2A>- und die <xref:System.Drawing.Size.Height%2A>-Eigenschaft fest.

Im folgenden Codebeispiel wird das Formular mit einer Breite angezeigt, die um 200 Pixel größer ist als die aktuelle Einstellung.

```vb
Form1.Width += 200
```

```csharp
Form1.Width += 200;
```

```cpp
Form1->Width += 200;
```

> [!CAUTION]
> Sie sollten immer die <xref:System.Drawing.Size.Height%2A>- oder die <xref:System.Drawing.Size.Width%2A>-Eigenschaft verwenden, um ein Maß eines Formulars zu ändern, es sei denn, Sie legen das Höhen- und das Breitenmaß gleichzeitig fest, indem Sie die <xref:System.Windows.Forms.Form.Size%2A>-Eigenschaft auf eine neue <xref:System.Drawing.Size>-Struktur festlegen. Die <xref:System.Windows.Forms.Form.Size%2A>-Eigenschaft gibt eine <xref:System.Drawing.Size>-Struktur zurück, die ein Werttyp ist. Sie können der Eigenschaft eines Werttyps keinen neuen Wert zuweisen. Daher kann das folgende Codebeispiel nicht kompiliert werden.

```vb
' NOTE: CODE WILL NOT COMPILE
Dim f As New Form()
f.Size.Width += 100
```

```csharp
// NOTE: CODE WILL NOT COMPILE
Form f = new Form();
f.Size.Width += 100;
```

```cpp
// NOTE: CODE WILL NOT COMPILE
Form^ f = gcnew Form();
f->Size->X += 100;
```

## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit Windows Forms](getting-started-with-windows-forms.md)
- [Erweitern von Windows Forms-Anwendungen](./advanced/index.md)
