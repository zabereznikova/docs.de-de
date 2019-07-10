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
ms.openlocfilehash: 135938c4ed91423145ca46b743620f4236f7f818
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742259"
---
# <a name="assemblyattributesgoheres"></a><span data-ttu-id="c2343-102">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="c2343-102">AssemblyAttributesGoHereS</span></span>

<span data-ttu-id="c2343-103">Wird von ALink als Platzhalter verwendet, um Informationen über benutzerdefinierte Attribute zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c2343-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="c2343-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2343-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHereS
```

## <a name="remarks"></a><span data-ttu-id="c2343-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2343-105">Remarks</span></span>

<span data-ttu-id="c2343-106">Verweise auf diesen Typ können in NETMODULE-Dateien eingebettet sein, deren Quellen benutzerdefinierte Assemblyattribute enthalten.</span><span class="sxs-lookup"><span data-stu-id="c2343-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="c2343-107">Beim Erstellen eines Assemblymanifests aus mindestens einer NETMODULE-Datei, die Verweise auf diese Typen enthält, verwendet ALink die zu diesen Verweisen gehörenden Informationen, um echte benutzerdefinierte Attribute auszugeben.</span><span class="sxs-lookup"><span data-stu-id="c2343-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="c2343-108">Daher wird dieser Typ nie instanziiert, und Verweise auf diesen Typ werden nur als Teil des Buildprozesses verwendet und erfüllen in der endgültigen Assembly keinen Zweck.</span><span class="sxs-lookup"><span data-stu-id="c2343-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="c2343-109">Verweise auf diesen Typ geben benutzerdefinierte Attribute an, die sicherheitsrelevant sind und nicht mehrfach verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c2343-109">References to this type indicate custom attributes that are security related and are not multiple-use.</span></span>

<span data-ttu-id="c2343-110">Diese Typen sind "intern" in .NET Framework markiert, und befinden sich in der <xref:System.Runtime.CompilerServices> Namespace.</span><span class="sxs-lookup"><span data-stu-id="c2343-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="c2343-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2343-111">Requirements</span></span>

<span data-ttu-id="c2343-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="c2343-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="c2343-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2343-113">See also</span></span>

- [<span data-ttu-id="c2343-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="c2343-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="c2343-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="c2343-115">AssemblyAttributesGoHereM</span></span>](assemblyattributesgoherem.md)
- [<span data-ttu-id="c2343-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="c2343-116">AssemblyAttributesGoHereSM</span></span>](assemblyattributesgoheresm.md)
