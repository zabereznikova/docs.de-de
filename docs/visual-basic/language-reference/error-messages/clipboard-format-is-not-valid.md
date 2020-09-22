---
title: Das Format der Zwischenablage ist ungültig.
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 429d1e120a0044152a358a87663eb09989f45b0e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874593"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="a2136-102">Das Format der Zwischenablage ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="a2136-102">Clipboard format is not valid</span></span>

<span data-ttu-id="a2136-103">Das angegebene Zwischenablage Format ist mit der ausgeführten Methode nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="a2136-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="a2136-104">Zu den möglichen Ursachen für diesen Fehler gehören:</span><span class="sxs-lookup"><span data-stu-id="a2136-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="a2136-105">Verwenden der-oder-Methode der Zwischenablage `GetText` `SetText` mit einem anderen Zwischenablage Format als `vbCFText` oder `vbCFLink` .</span><span class="sxs-lookup"><span data-stu-id="a2136-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
- <span data-ttu-id="a2136-106">Verwenden der-oder-Methode der Zwischenablage `GetData` `SetData` mit einem anderen Zwischenablage Format als `vbCFBitmap` , `vbCFDIB` oder `vbCFMetafile` .</span><span class="sxs-lookup"><span data-stu-id="a2136-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
- <span data-ttu-id="a2136-107">Verwenden der `GetData` - `SetData` Methode oder der-Methode eines `DataObject` mit einem Zwischenablage Format in dem von Microsoft Windows reservierten Bereich für registrierte Formate (&HC000-&HFFFF), wenn dieses Zwischenablage Format nicht bei Microsoft Windows registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="a2136-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a2136-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a2136-108">To correct this error</span></span>  
  
- <span data-ttu-id="a2136-109">Entfernen Sie das ungültige Format, und geben Sie ein gültiges Format an.</span><span class="sxs-lookup"><span data-stu-id="a2136-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2136-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a2136-110">See also</span></span>

- [<span data-ttu-id="a2136-111">Zwischenablage: Hinzufügen anderer Formate</span><span class="sxs-lookup"><span data-stu-id="a2136-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
