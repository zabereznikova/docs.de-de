---
title: ISymUnmanagedWriter4-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: eaf2e8e60d9812ab6a31fb3b9050cbaae0f1a9d7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609468"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="bc405-102">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc405-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="bc405-103">ISymUnmanagedWriter4-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="bc405-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc405-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc405-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="bc405-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="bc405-105">Methods</span></span>  
 <span data-ttu-id="bc405-106">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="bc405-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="bc405-107">Methode</span><span class="sxs-lookup"><span data-stu-id="bc405-107">Method</span></span>|<span data-ttu-id="bc405-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bc405-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc405-109">GetDebugInfoWithPadding-Methode</span><span class="sxs-lookup"><span data-stu-id="bc405-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="bc405-110">Funktioniert genauso wie die [GetDebugInfo-Methode](isymunmanagedwriter-getdebuginfo-method.md) , mit der Ausnahme, dass die Pfad Zeichenfolge nach dem abschließenden NULL-Zeichen mit Nullen aufgefüllt wird, damit die Zeichen folgen Daten eine festgelegte Größe von haben `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="bc405-110">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="bc405-111">Padding wird nur angegeben, wenn die Länge der Pfad Zeichenfolge selbst kleiner als ist `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="bc405-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="bc405-112">Dadurch wird das Schreiben von Tools erleichtert, die PE-Dateien unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="bc405-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc405-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc405-113">Requirements</span></span>  
 <span data-ttu-id="bc405-114">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="bc405-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc405-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc405-115">See also</span></span>

- [<span data-ttu-id="bc405-116">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bc405-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="bc405-117">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc405-117">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
