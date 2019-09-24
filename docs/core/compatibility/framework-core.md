---
title: 'Breaking Changes, .NET Framework zu .NET Core 3.0: .NET Core'
description: Listet die Breaking Changes von .NET Framework zu .NET Core 3.0 für Windows Forms und Windows Presentation Foundation auf.
ms.date: 09/10/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c658c5bce7a2554bba83f2779a73d9d6af01a342
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "71151533"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core-30"></a><span data-ttu-id="0d4a5-103">Breaking Changes für die Migration von .NET Framework 3.0 zu .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0d4a5-103">Breaking changes for migration from .NET Framework to .NET Core 3.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d4a5-104">Dieser Artikel wird aktuell überarbeitet.</span><span class="sxs-lookup"><span data-stu-id="0d4a5-104">This article is under construction.</span></span> <span data-ttu-id="0d4a5-105">Nicht alle Breaking Changes für .NET Core werden hier aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0d4a5-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="0d4a5-106">Weitere Informationen zu Breaking Changes für .NET Core finden Sie in den jeweiligen [Issues zu Breaking Changes](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) im Repository „dotnet/docs“ auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="0d4a5-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span> 

<span data-ttu-id="0d4a5-107">Wenn Sie eine Windows Forms- oder Windows Presentation Foundation-Anwendung von .NET Framework zu .NET Core 3.0 migrieren, finden Sie in den folgenden Themen Breaking Changes, die sich auf Ihre App auswirken können:</span><span class="sxs-lookup"><span data-stu-id="0d4a5-107">If you are migrating a Windows Forms or Windows Presentation Foundation application from .NET Framework to .NET Core 3.0, review the following topics for breaking changes that may affect your app:</span></span>

## <a name="windows-forms"></a><span data-ttu-id="0d4a5-108">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0d4a5-108">Windows Forms</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacyimages.md)]
