---
title: Line-Anweisungen werden nicht mehr unterstützt (Visual Basic-Compilerfehler)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 4ca1538dbde0d585b7b421d60cde4531c00e9145
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873833"
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
