---
title: Breaking Changes bei Windows Forms – .NET Core
description: Listet die Breaking Changes bei Windows Forms für .NET Core auf.
ms.date: 09/20/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 436088836ff5441e426379bb41f96821cbc7e500
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71272721"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="c2b79-103">Breaking Changes bei Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c2b79-103">Breaking changes in Windows Forms</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2b79-104">Dieser Artikel wird aktuell überarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c2b79-104">This article is under construction.</span></span> <span data-ttu-id="c2b79-105">Nicht alle Breaking Changes für .NET Core werden hier aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2b79-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="c2b79-106">Weitere Informationen zu Breaking Changes für .NET Core finden Sie in den jeweiligen [Issues zu Breaking Changes](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) im Repository „dotnet/docs“ auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="c2b79-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span>

<span data-ttu-id="c2b79-107">Im Folgenden sind die Breaking Changes bei Windows Forms in .NET Core aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c2b79-107">The following is a list of breaking changes in Windows Forms by .NET Core version.</span></span>

## <a name="net-core-30-preview-9"></a><span data-ttu-id="c2b79-108">.NET Core 3.0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="c2b79-108">.NET Core 3.0 Preview 9</span></span>

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacyimages.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/remove-serializationattribute.md)]

## <a name="net-core-30"></a><span data-ttu-id="c2b79-109">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c2b79-109">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/modernized-folderbrowserdialog.md)]
