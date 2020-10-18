---
title: Line-Anweisungen werden nicht mehr unterstützt (Visual Basic-Compilerfehler)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: f34095becf321c6cb4b316b6378a2da0107577ba
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162478"
---
# <a name="bc30830-line-statements-are-no-longer-supported"></a>BC30830: "Line"-Anweisungen werden nicht mehr unterstützt.

Line-Anweisungen werden nicht mehr unterstützt. Die Datei-e/a-Funktionalität ist als verfügbar, `Microsoft.VisualBasic.FileSystem.LineInput` und die Grafik Funktionalität ist als verfügbar `System.Drawing.Graphics.DrawLine` .

 **Fehler-ID:** BC30830

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Wenn Sie Dateizugriff durchführen, verwenden Sie `Microsoft.VisualBasic.FileSystem.LineInput` .

- Verwenden Sie `System.Drawing.Graphics.Drawline`für Grafikfunktionen.

## <a name="see-also"></a>Siehe auch

- <xref:System.IO>
- <xref:System.Drawing>
- [Dateizugriff mit Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)
