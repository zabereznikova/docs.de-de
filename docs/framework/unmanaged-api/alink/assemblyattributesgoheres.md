---
title: AssemblyAttributesGoHereS
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereS
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereS
helpviewer_keywords:
- AssemblyAttributesGoHereS type
- Alink API, AssemblyAttributesGoHereS type
ms.assetid: 4e817f35-a2bc-4403-9e6f-f731e6b9fe23
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74447f52c75ae22e513c6f07950630d37bad191a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969829"
---
# <a name="assemblyattributesgoheres"></a><span data-ttu-id="a2ffc-102">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="a2ffc-102">AssemblyAttributesGoHereS</span></span>

<span data-ttu-id="a2ffc-103">Wird von ALink als Platzhalter verwendet, um Informationen über benutzerdefinierte Attribute zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a2ffc-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2ffc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2ffc-104">Syntax</span></span>

```
internal sealed class AssemblyAttributesGoHereS
```

## <a name="remarks"></a><span data-ttu-id="a2ffc-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2ffc-105">Remarks</span></span>

<span data-ttu-id="a2ffc-106">Verweise auf diesen Typ können in NETMODULE-Dateien eingebettet sein, deren Quellen benutzerdefinierte Assemblyattribute enthalten.</span><span class="sxs-lookup"><span data-stu-id="a2ffc-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="a2ffc-107">Beim Erstellen eines Assemblymanifests aus mindestens einer NETMODULE-Datei, die Verweise auf diese Typen enthält, verwendet ALink die zu diesen Verweisen gehörenden Informationen, um echte benutzerdefinierte Attribute auszugeben.</span><span class="sxs-lookup"><span data-stu-id="a2ffc-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="a2ffc-108">Daher wird dieser Typ nie instanziiert, und Verweise auf diesen Typ werden nur als Teil des Buildprozesses verwendet und erfüllen in der endgültigen Assembly keinen Zweck.</span><span class="sxs-lookup"><span data-stu-id="a2ffc-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="a2ffc-109">Verweise auf diesen Typ geben benutzerdefinierte Attribute an, die sicherheitsrelevant sind und nicht mehrfach verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a2ffc-109">References to this type indicate custom attributes that are security related and are not multiple-use.</span></span>

<span data-ttu-id="a2ffc-110">Diese Typen sind "intern" in .NET Framework markiert, und befinden sich in der <xref:System.Runtime.CompilerServices> Namespace.</span><span class="sxs-lookup"><span data-stu-id="a2ffc-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="a2ffc-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a2ffc-111">Requirements</span></span>

<span data-ttu-id="a2ffc-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="a2ffc-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="a2ffc-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2ffc-113">See also</span></span>

- [<span data-ttu-id="a2ffc-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="a2ffc-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="a2ffc-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="a2ffc-115">AssemblyAttributesGoHereM</span></span>](assemblyattributesgoherem.md)
- [<span data-ttu-id="a2ffc-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="a2ffc-116">AssemblyAttributesGoHereSM</span></span>](assemblyattributesgoheresm.md)
