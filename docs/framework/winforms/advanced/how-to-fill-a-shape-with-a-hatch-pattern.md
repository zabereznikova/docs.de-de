---
title: 'Vorgehensweise: Ausfüllen einer Form mit einer Schraffur'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: b9ecefb82aaaf896c4ed39733f1e8d7bd65c16d4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645468"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>Vorgehensweise: Ausfüllen einer Form mit einer Schraffur
Eine Schraffur besteht aus zwei Farben: eine für den Hintergrund und eine für die Zeilen, die über dem Hintergrund der Muster bilden. Um eine geschlossene Form mit einer Schraffur zu füllen, verwenden eine <xref:System.Drawing.Drawing2D.HatchBrush> Objekt. Im folgenden Beispiel wird veranschaulicht, wie eine Ellipse mit einer Schraffur füllen:  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> Konstruktor akzeptiert drei Argumente: die Schraffurart, die Farbe der Schraffurlinie und die Farbe des Hintergrunds. Das Schraffurstilargument möglich einen beliebigen Wert aus der <xref:System.Drawing.Drawing2D.HatchStyle> Enumeration. Es gibt mehr als 50 Elemente in der <xref:System.Drawing.Drawing2D.HatchStyle> Enumeration; einige davon Elemente sind in der folgenden Liste dargestellt:  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 Die folgende Abbildung zeigt die ausgefüllte Ellipse.  
  
 ![Muster Schraffieren](./media/hatch1.png "hatch1")  
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden eines Pinsels zum Ausfüllen von Formen](using-a-brush-to-fill-shapes.md)
