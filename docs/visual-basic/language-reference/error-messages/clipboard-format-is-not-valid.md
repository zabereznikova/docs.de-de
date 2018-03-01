---
title: "Das Format der Zwischenablage ist ungültig."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7adc417d962de35272319d7dc976b237c7e2b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="e5716-102">Das Format der Zwischenablage ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="e5716-102">Clipboard format is not valid</span></span>
<span data-ttu-id="e5716-103">Das angegebene Format der Zwischenablage ist nicht kompatibel mit der Methode, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e5716-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="e5716-104">Zu den möglichen Ursachen für diesen Fehler sind:</span><span class="sxs-lookup"><span data-stu-id="e5716-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="e5716-105">Verwenden der Zwischenablage `GetText` oder `SetText` Methode mit einem Zwischenablageformat außer `vbCFText` oder `vbCFLink`.</span><span class="sxs-lookup"><span data-stu-id="e5716-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
-   <span data-ttu-id="e5716-106">Verwenden der Zwischenablage `GetData` oder `SetData` Methode mit einem Zwischenablageformat außer `vbCFBitmap`, `vbCFDIB`, oder `vbCFMetafile`.</span><span class="sxs-lookup"><span data-stu-id="e5716-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
-   <span data-ttu-id="e5716-107">Mithilfe der `DataObject``GetData` Methode oder `SetData` Methode mit einem Zwischenablageformat im Bereich von Microsoft Windows für registrierte Formate (& HC000- & HFFFF reserviert), wenn dieses Format der Zwischenablage wurde noch nicht registriert mit Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="e5716-107">Using the `DataObject``GetData` method or `SetData` method with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e5716-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="e5716-108">To correct this error</span></span>  
  
-   <span data-ttu-id="e5716-109">Entfernen Sie das ungültige Format, und geben Sie einen gültigen.</span><span class="sxs-lookup"><span data-stu-id="e5716-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5716-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5716-110">See Also</span></span>  
 [<span data-ttu-id="e5716-111">Zwischenablage: Hinzufügen anderer Formate</span><span class="sxs-lookup"><span data-stu-id="e5716-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
