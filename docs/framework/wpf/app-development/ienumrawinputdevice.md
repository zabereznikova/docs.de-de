---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 2030ad0ac00419280b45555ff11495c74e4274e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547784"
---
# <a name="ienumrawinputdevice"></a><span data-ttu-id="9cc70-102">IEnumRAWINPUTDEVICE</span><span class="sxs-lookup"><span data-stu-id="9cc70-102">IEnumRAWINPUTDEVICE</span></span>
<span data-ttu-id="9cc70-103">Diese Schnittstelle listet die Geräte für die unformatierte Eingabe auf und wird nur von "PresentationHost.exe" verwendet.</span><span class="sxs-lookup"><span data-stu-id="9cc70-103">This interface enumerates the raw input devices, and is only used by PresentationHost.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9cc70-104">Diese API ist nur für die Verwendung auf dem lokalen Clientcomputer vorgesehen und wird nur zu diesem Zweck unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9cc70-104">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="9cc70-105">Member</span><span class="sxs-lookup"><span data-stu-id="9cc70-105">Members</span></span>  
  
|<span data-ttu-id="9cc70-106">Member</span><span class="sxs-lookup"><span data-stu-id="9cc70-106">Member</span></span>|<span data-ttu-id="9cc70-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9cc70-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9cc70-108">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="9cc70-108">IEnumRAWINPUTDEVIC:Next</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)|<span data-ttu-id="9cc70-109">Listet die nächsten `celt`-Elemente (RAWINPUTDEVICE-Strukturen) in der Liste des Enumerators auf, wobei die Rückgabe in `rgelt` zusammen mit der tatsächlichen Anzahl der aufgelisteten Elemente in `pceltFetched` erfolgt.</span><span class="sxs-lookup"><span data-stu-id="9cc70-109">Enumerates the next `celt` elements (that is, RAWINPUTDEVICE structures) in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>|  
|[<span data-ttu-id="9cc70-110">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="9cc70-110">IEnumRAWINPUTDEVIC:Skip</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-skip.md)|<span data-ttu-id="9cc70-111">Weist den Enumerator auf das nächste überspringen `celt` Elemente in der Enumeration, damit der nächste Aufruf von [Ienumrawinputdevic](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) diese Elemente werden nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9cc70-111">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) will not return those elements.</span></span>|  
|[<span data-ttu-id="9cc70-112">IEnumRAWINPUTDEVIC:Reset</span><span class="sxs-lookup"><span data-stu-id="9cc70-112">IEnumRAWINPUTDEVIC:Reset</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-reset.md)|<span data-ttu-id="9cc70-113">Setzt die Enumerationsfolge auf den Anfang zurück.</span><span class="sxs-lookup"><span data-stu-id="9cc70-113">Resets the enumeration sequence to the beginning.</span></span>|  
|[<span data-ttu-id="9cc70-114">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="9cc70-114">IEnumRAWINPUTDEVIC:Clone</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-clone.md)|<span data-ttu-id="9cc70-115">Erstellt einen weiteren Enumerator für Geräte für die unformatierte Eingabe, der denselben Zustand wie der aktuelle Enumerator aufweist und dieselbe Liste durchlaufen soll.</span><span class="sxs-lookup"><span data-stu-id="9cc70-115">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9cc70-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cc70-116">See Also</span></span>  
 [<span data-ttu-id="9cc70-117">Informationen zur unformatierten Eingabe</span><span class="sxs-lookup"><span data-stu-id="9cc70-117">About Raw Input</span></span>](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/aboutrawinput.asp)
