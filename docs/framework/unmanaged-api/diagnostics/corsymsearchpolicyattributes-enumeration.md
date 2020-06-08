---
title: CorSymSearchPolicyAttributes-Enumeration
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
ms.openlocfilehash: 8af71314cf8a24c710d3b8980c082daaf9186715
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501871"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="fff99-102">CorSymSearchPolicyAttributes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fff99-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="fff99-103">Gibt die Richtlinie an, die bei einer Suche nach einem Symbol Leser verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fff99-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="fff99-104">Diese Konstanten werden von der [ISymUnmanagedBinder2:: GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) -Methode und der [ISymUnmanagedBinder3:: GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="fff99-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fff99-105">Es ist ein Sicherheitsrisiko, eine Programm Datenbankdatei (PDB-Datei) aus einer nicht vertrauenswürdigen Quelle zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fff99-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fff99-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fff99-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="fff99-107">Member</span><span class="sxs-lookup"><span data-stu-id="fff99-107">Members</span></span>  
  
|<span data-ttu-id="fff99-108">Member</span><span class="sxs-lookup"><span data-stu-id="fff99-108">Member</span></span>|<span data-ttu-id="fff99-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fff99-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="fff99-110">Fragt die Registrierung nach Symbol Suchpfaden ab.</span><span class="sxs-lookup"><span data-stu-id="fff99-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="fff99-111">Greift auf einen Symbol Server zu.</span><span class="sxs-lookup"><span data-stu-id="fff99-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="fff99-112">Durchsucht den im Debug-Verzeichnis angegebenen Pfad.</span><span class="sxs-lookup"><span data-stu-id="fff99-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="fff99-113">Sucht die PDB an der Stelle, an der die exe-Datei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="fff99-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fff99-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fff99-114">Requirements</span></span>  
 <span data-ttu-id="fff99-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="fff99-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fff99-116">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="fff99-116">See also</span></span>

- [<span data-ttu-id="fff99-117">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="fff99-117">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
