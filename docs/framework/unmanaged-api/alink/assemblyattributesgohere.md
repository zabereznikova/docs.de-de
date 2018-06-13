---
title: AssemblyAttributesGoHere
ms.date: 03/30/2017
api_name:
- AssemblyAttributesGoHere
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyAttributesGoHere
helpviewer_keywords:
- AssemblyAttributesGoHere type
- Alink API, AssemblyAttributesGoHere type
ms.assetid: 7b26fcb6-94f4-4f09-933e-b33efe451f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c24ca43f35e237b6387e108563b1f9c9ed432242
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402394"
---
# <a name="assemblyattributesgohere"></a><span data-ttu-id="6f583-102">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="6f583-102">AssemblyAttributesGoHere</span></span>
<span data-ttu-id="6f583-103">Wird von ALink als Platzhalter verwendet, um Informationen über benutzerdefinierte Attribute zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6f583-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f583-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f583-104">Syntax</span></span>  
  
```  
AssemblyAttributesGoHere  
```  
  
## <a name="remarks"></a><span data-ttu-id="6f583-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f583-105">Remarks</span></span>  
 <span data-ttu-id="6f583-106">Verweise auf diesen Typ können in NETMODULE-Dateien eingebettet sein, deren Quellen benutzerdefinierte Assemblyattribute enthalten.</span><span class="sxs-lookup"><span data-stu-id="6f583-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="6f583-107">Beim Erstellen eines Assemblymanifests aus mindestens einer NETMODULE-Datei, die Verweise auf diese Typen enthält, verwendet ALink die zu diesen Verweisen gehörenden Informationen, um echte benutzerdefinierte Attribute auszugeben.</span><span class="sxs-lookup"><span data-stu-id="6f583-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="6f583-108">Daher wird dieser Typ nie instanziiert, und Verweise auf diesen Typ werden nur als Teil des Buildprozesses verwendet und erfüllen in der endgültigen Assembly keinen Zweck.</span><span class="sxs-lookup"><span data-stu-id="6f583-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="6f583-109">Verweise auf diesen Typ geben benutzerdefinierte Attribute an, die nicht sicherheitsrelevant sind und nicht mehrfach verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6f583-109">References to this type indicate custom attributes that are not security related and are not multiple-use.</span></span>  
  
 <span data-ttu-id="6f583-110">Diese Typen sind in .NET Framework mit "intern" markiert und befinden sich in <xref:System.Runtime.CompilerServices>.</span><span class="sxs-lookup"><span data-stu-id="6f583-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f583-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6f583-111">Requirements</span></span>  
 <span data-ttu-id="6f583-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="6f583-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f583-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f583-113">See Also</span></span>  
 [<span data-ttu-id="6f583-114">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="6f583-114">AssemblyAttributesGoHereM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)  
 [<span data-ttu-id="6f583-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="6f583-115">AssemblyAttributesGoHereS</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheres.md)  
 [<span data-ttu-id="6f583-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="6f583-116">AssemblyAttributesGoHereSM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
