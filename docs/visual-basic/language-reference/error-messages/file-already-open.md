---
title: Die Datei ist bereits geöffnet.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 97f9e13e6802e793f7c7baf1f03ec51205eb6d42
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874177"
---
# <a name="file-already-open"></a><span data-ttu-id="329eb-102">Die Datei ist bereits geöffnet.</span><span class="sxs-lookup"><span data-stu-id="329eb-102">File already open</span></span>

<span data-ttu-id="329eb-103">Manchmal muss eine Datei geschlossen werden, bevor ein anderer `FileOpen` oder ein anderer Vorgang ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="329eb-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="329eb-104">Zu den möglichen Ursachen für diesen Fehler gehören:</span><span class="sxs-lookup"><span data-stu-id="329eb-104">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="329eb-105">`FileOpen`Für eine Datei, die bereits geöffnet ist, wurde ein sequenzieller Ausgabemodus ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="329eb-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
- <span data-ttu-id="329eb-106">Eine-Anweisung verweist auf eine geöffnete Datei.</span><span class="sxs-lookup"><span data-stu-id="329eb-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="329eb-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="329eb-107">To correct this error</span></span>  
  
1. <span data-ttu-id="329eb-108">Schließen Sie die Datei, bevor Sie die Anweisung ausführen.</span><span class="sxs-lookup"><span data-stu-id="329eb-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="329eb-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="329eb-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
