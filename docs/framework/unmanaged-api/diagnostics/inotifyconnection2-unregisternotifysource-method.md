---
title: INotifyConnection2::UnregisterNotifySource-Methode
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
ms.openlocfilehash: 90220c2bfea683ff0472473e180c9e11ea568672
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720034"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="53821-102">INotifyConnection2::UnregisterNotifySource-Methode</span><span class="sxs-lookup"><span data-stu-id="53821-102">INotifyConnection2::UnregisterNotifySource Method</span></span>

<span data-ttu-id="53821-103">Entfernt ein angegebenes Benachrichtigungs Quell Objekt aus der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="53821-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53821-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53821-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53821-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="53821-105">Parameters</span></span>  

 `in_pNotifySource`  
 <span data-ttu-id="53821-106">in Benachrichtigungs Objekt, deren Registrierung aufgehoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="53821-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53821-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="53821-107">Return Value</span></span>  

 <span data-ttu-id="53821-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="53821-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53821-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="53821-109">Requirements</span></span>  

 <span data-ttu-id="53821-110">**Header:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="53821-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53821-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53821-111">See also</span></span>

- [<span data-ttu-id="53821-112">INotifyConnection2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53821-112">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
- [<span data-ttu-id="53821-113">INotifySource2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53821-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="53821-114">INotifySink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53821-114">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="53821-115">RegisterNotifySource-Methode</span><span class="sxs-lookup"><span data-stu-id="53821-115">RegisterNotifySource Method</span></span>](inotifyconnection2-registernotifysource-method.md)
