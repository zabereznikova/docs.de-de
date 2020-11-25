---
title: ISymUnmanagedReader2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: 3f34be833d3ccb5c636d2c5f18ccb6e216ef2c49
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709075"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="eddb5-102">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eddb5-102">ISymUnmanagedReader2 Interface</span></span>

<span data-ttu-id="eddb5-103">Stellt einen Symbolreader dar, der Zugriff auf Dokumente, Methoden und Variablen innerhalb eines Symbolspeichers bietet.</span><span class="sxs-lookup"><span data-stu-id="eddb5-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="eddb5-104">Diese Schnittstelle erweitert die [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="eddb5-104">This interface extends the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eddb5-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="eddb5-105">Methods</span></span>  
  
|<span data-ttu-id="eddb5-106">Methode</span><span class="sxs-lookup"><span data-stu-id="eddb5-106">Method</span></span>|<span data-ttu-id="eddb5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="eddb5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eddb5-108">GetMethodByVersionPreRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="eddb5-108">GetMethodByVersionPreRemap Method</span></span>](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="eddb5-109">Sie erhalten eine Symbol Lesemethode, wenn Sie über ein Methoden Token und eine Edit-and-Continue-Versionsnummer verfügen.</span><span class="sxs-lookup"><span data-stu-id="eddb5-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="eddb5-110">GetMethodsInDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="eddb5-110">GetMethodsInDocument Method</span></span>](isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="eddb5-111">Ruft jede Methode ab, die im angegebenen Dokument über Zeilen Informationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="eddb5-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="eddb5-112">GetSymAttributePreRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="eddb5-112">GetSymAttributePreRemap Method</span></span>](isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="eddb5-113">Ruft ein benutzerdefiniertes Attribut basierend auf seinem Namen ab.</span><span class="sxs-lookup"><span data-stu-id="eddb5-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eddb5-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="eddb5-114">Requirements</span></span>  

 <span data-ttu-id="eddb5-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="eddb5-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eddb5-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eddb5-116">See also</span></span>

- [<span data-ttu-id="eddb5-117">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="eddb5-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="eddb5-118">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eddb5-118">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
