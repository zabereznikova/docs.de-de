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
# <a name="bc30830-line-statements-are-no-longer-supported"></a><span data-ttu-id="25ef9-102">BC30830: "Line"-Anweisungen werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25ef9-102">BC30830: 'Line' statements are no longer supported</span></span>

<span data-ttu-id="25ef9-103">Line-Anweisungen werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25ef9-103">Line statements are no longer supported.</span></span> <span data-ttu-id="25ef9-104">Die Datei-e/a-Funktionalität ist als verfügbar, `Microsoft.VisualBasic.FileSystem.LineInput` und die Grafik Funktionalität ist als verfügbar `System.Drawing.Graphics.DrawLine` .</span><span class="sxs-lookup"><span data-stu-id="25ef9-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>

 <span data-ttu-id="25ef9-105">**Fehler-ID:** BC30830</span><span class="sxs-lookup"><span data-stu-id="25ef9-105">**Error ID:** BC30830</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="25ef9-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="25ef9-106">To correct this error</span></span>

- <span data-ttu-id="25ef9-107">Wenn Sie Dateizugriff durchführen, verwenden Sie `Microsoft.VisualBasic.FileSystem.LineInput` .</span><span class="sxs-lookup"><span data-stu-id="25ef9-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>

- <span data-ttu-id="25ef9-108">Verwenden Sie `System.Drawing.Graphics.Drawline`für Grafikfunktionen.</span><span class="sxs-lookup"><span data-stu-id="25ef9-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>

## <a name="see-also"></a><span data-ttu-id="25ef9-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25ef9-109">See also</span></span>

- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="25ef9-110">Dateizugriff mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="25ef9-110">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
