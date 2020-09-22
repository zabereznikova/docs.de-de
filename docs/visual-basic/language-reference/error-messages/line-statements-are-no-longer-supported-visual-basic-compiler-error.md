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
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a><span data-ttu-id="dc551-102">Line-Anweisungen werden nicht mehr unterstützt (Visual Basic-Compilerfehler)</span><span class="sxs-lookup"><span data-stu-id="dc551-102">'Line' statements are no longer supported (Visual Basic Compiler Error)</span></span>

<span data-ttu-id="dc551-103">Line-Anweisungen werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dc551-103">Line statements are no longer supported.</span></span> <span data-ttu-id="dc551-104">Die Datei-e/a-Funktionalität ist als verfügbar, `Microsoft.VisualBasic.FileSystem.LineInput` und die Grafik Funktionalität ist als verfügbar `System.Drawing.Graphics.DrawLine` .</span><span class="sxs-lookup"><span data-stu-id="dc551-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>  
  
 <span data-ttu-id="dc551-105">**Fehler-ID:** BC30830</span><span class="sxs-lookup"><span data-stu-id="dc551-105">**Error ID:** BC30830</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dc551-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="dc551-106">To correct this error</span></span>  
  
1. <span data-ttu-id="dc551-107">Wenn Sie Dateizugriff durchführen, verwenden Sie `Microsoft.VisualBasic.FileSystem.LineInput` .</span><span class="sxs-lookup"><span data-stu-id="dc551-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>  
  
2. <span data-ttu-id="dc551-108">Verwenden Sie `System.Drawing.Graphics.Drawline`für Grafikfunktionen.</span><span class="sxs-lookup"><span data-stu-id="dc551-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc551-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc551-109">See also</span></span>

- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="dc551-110">Dateizugriff mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dc551-110">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
