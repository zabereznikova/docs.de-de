---
title: AssemblyAttributesGoHereM Class (System.Runtime.CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereM
helpviewer_keywords:
- AssemblyAttributesGoHereM type
- Alink API, AssemblyAttributesGoHereM type
ms.assetid: caaa8ba9-b4bb-4dd6-934d-57e436b2f3e5
topic_type:
- apiref
ms.openlocfilehash: 15b9445aa3eabbd14541cfe5481bfb553c8c0347
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446632"
---
# <a name="assemblyattributesgoherem-class"></a><span data-ttu-id="3b1f6-102">AssemblyAttributesGoHereM Class</span><span class="sxs-lookup"><span data-stu-id="3b1f6-102">AssemblyAttributesGoHereM Class</span></span>

<span data-ttu-id="3b1f6-103">Wird von ALink als Platzhalter verwendet, um Informationen über benutzerdefinierte Attribute zu speichern.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="3b1f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b1f6-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHereM
```

## <a name="remarks"></a><span data-ttu-id="3b1f6-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3b1f6-105">Remarks</span></span>

<span data-ttu-id="3b1f6-106">Verweise auf diesen Typ können in NETMODULE-Dateien eingebettet sein, deren Quellen benutzerdefinierte Assemblyattribute enthalten.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="3b1f6-107">Beim Erstellen eines Assemblymanifests aus mindestens einer NETMODULE-Datei, die Verweise auf diese Typen enthält, verwendet ALink die zu diesen Verweisen gehörenden Informationen, um echte benutzerdefinierte Attribute auszugeben.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="3b1f6-108">Daher wird dieser Typ nie instanziiert, und Verweise auf diesen Typ werden nur als Teil des Buildprozesses verwendet und erfüllen in der endgültigen Assembly keinen Zweck.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="3b1f6-109">Verweise auf diesen Typ geben benutzerdefinierte Attribute an, die nicht sicherheitsrelevant sind, aber mehrfach verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-109">References to this type indicate custom attributes that are not security related but are multiple-use.</span></span>

<span data-ttu-id="3b1f6-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span><span class="sxs-lookup"><span data-stu-id="3b1f6-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="3b1f6-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3b1f6-111">Requirements</span></span>

<span data-ttu-id="3b1f6-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="3b1f6-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="3b1f6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b1f6-113">See also</span></span>

- [<span data-ttu-id="3b1f6-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="3b1f6-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="3b1f6-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="3b1f6-115">AssemblyAttributesGoHereS</span></span>](assemblyattributesgoheres.md)
- [<span data-ttu-id="3b1f6-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="3b1f6-116">AssemblyAttributesGoHereSM</span></span>](assemblyattributesgoheresm.md)
