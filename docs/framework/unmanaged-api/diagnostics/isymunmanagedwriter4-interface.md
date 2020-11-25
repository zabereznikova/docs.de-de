---
title: ISymUnmanagedWriter4-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: c2b57897e4f0e8b23337302f344065d79677e0c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725806"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="041b2-102">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="041b2-102">ISymUnmanagedWriter4 Interface</span></span>

<span data-ttu-id="041b2-103">ISymUnmanagedWriter4-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="041b2-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="041b2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="041b2-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="041b2-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="041b2-105">Methods</span></span>  

 <span data-ttu-id="041b2-106">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="041b2-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="041b2-107">Methode</span><span class="sxs-lookup"><span data-stu-id="041b2-107">Method</span></span>|<span data-ttu-id="041b2-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="041b2-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="041b2-109">GetDebugInfoWithPadding-Methode</span><span class="sxs-lookup"><span data-stu-id="041b2-109">GetDebugInfoWithPadding Method</span></span>](isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="041b2-110">Funktioniert genauso wie die [GetDebugInfo-Methode](isymunmanagedwriter-getdebuginfo-method.md) , mit der Ausnahme, dass die Pfad Zeichenfolge nach dem abschließenden NULL-Zeichen mit Nullen aufgefüllt wird, damit die Zeichen folgen Daten eine festgelegte Größe von haben `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="041b2-110">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="041b2-111">Padding wird nur angegeben, wenn die Länge der Pfad Zeichenfolge selbst kleiner als ist `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="041b2-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="041b2-112">Dadurch wird das Schreiben von Tools erleichtert, die PE-Dateien unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="041b2-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="041b2-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="041b2-113">Requirements</span></span>  

 <span data-ttu-id="041b2-114">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="041b2-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="041b2-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="041b2-115">See also</span></span>

- [<span data-ttu-id="041b2-116">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="041b2-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="041b2-117">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="041b2-117">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
