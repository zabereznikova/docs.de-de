---
title: Das Format der Zwischenablage ist ungültig.
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 15bc530d1030a8c4d720321ea249fdd7fb6cd8b6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623098"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="5b80f-102">Das Format der Zwischenablage ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="5b80f-102">Clipboard format is not valid</span></span>
<span data-ttu-id="5b80f-103">Das angegebene Zwischenablageformat ist nicht kompatibel mit der Methode ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5b80f-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="5b80f-104">Zu den möglichen Ursachen für diesen Fehler sind:</span><span class="sxs-lookup"><span data-stu-id="5b80f-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="5b80f-105">Verwenden der Zwischenablage des `GetText` oder `SetText` -Methode mit einem anderen Zwischenablageformat als `vbCFText` oder `vbCFLink`.</span><span class="sxs-lookup"><span data-stu-id="5b80f-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
- <span data-ttu-id="5b80f-106">Verwenden der Zwischenablage des `GetData` oder `SetData` -Methode mit einem anderen Zwischenablageformat als `vbCFBitmap`, `vbCFDIB`, oder `vbCFMetafile`.</span><span class="sxs-lookup"><span data-stu-id="5b80f-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
- <span data-ttu-id="5b80f-107">Mithilfe der `GetData` oder `SetData` Methoden eine `DataObject` mit einem Zwischenablageformat, in dem Bereich von Microsoft Windows für registrierte Formate (& HC000- & HFFFF reserviert), wenn dieses Format der Zwischenablage wurde nicht registriert mit Microsoft Windows .</span><span class="sxs-lookup"><span data-stu-id="5b80f-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5b80f-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5b80f-108">To correct this error</span></span>  
  
- <span data-ttu-id="5b80f-109">Entfernen Sie das ungültige Format, und geben Sie eine gültige Verbindungszeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="5b80f-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b80f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b80f-110">See also</span></span>

- [<span data-ttu-id="5b80f-111">Zwischenablage: Hinzufügen anderer Formate</span><span class="sxs-lookup"><span data-stu-id="5b80f-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
