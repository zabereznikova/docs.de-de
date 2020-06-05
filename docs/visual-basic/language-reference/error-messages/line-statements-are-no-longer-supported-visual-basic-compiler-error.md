---
title: Line-Anweisungen werden nicht mehr unterstützt (Visual Basic-Compilerfehler)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: a3d243f39f3fc45ca6b1ba0d26892d4c3db56f59
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397297"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a>Line-Anweisungen werden nicht mehr unterstützt (Visual Basic-Compilerfehler)
Line-Anweisungen werden nicht mehr unterstützt. Die Datei-e/a-Funktionalität ist als verfügbar, `Microsoft.VisualBasic.FileSystem.LineInput` und die Grafik Funktionalität ist als verfügbar `System.Drawing.Graphics.DrawLine` .  
  
 **Fehler-ID:** BC30830  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Wenn Sie Dateizugriff durchführen, verwenden Sie `Microsoft.VisualBasic.FileSystem.LineInput` .  
  
2. Verwenden Sie `System.Drawing.Graphics.Drawline`für Grafikfunktionen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IO>
- <xref:System.Drawing>
- [Dateizugriff mit Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)
