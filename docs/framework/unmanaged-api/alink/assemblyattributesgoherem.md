---
title: AssemblyAttributesGoHereM
ms.date: 03/30/2017
api_name:
- AssemblyAttributesGoHereM
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyAttributesGoHereM
helpviewer_keywords:
- AssemblyAttributesGoHereM type
- Alink API, AssemblyAttributesGoHereM type
ms.assetid: caaa8ba9-b4bb-4dd6-934d-57e436b2f3e5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bbd5428039144fd38796ed6865c24a605f236ccd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733804"
---
# <a name="assemblyattributesgoherem"></a>AssemblyAttributesGoHereM
Wird von ALink als Platzhalter verwendet, um Informationen über benutzerdefinierte Attribute zu speichern.  
  
## <a name="syntax"></a>Syntax  
  
```  
AssemblyAttributesGoHereM  
```  
  
## <a name="remarks"></a>Hinweise  
 Verweise auf diesen Typ können in NETMODULE-Dateien eingebettet sein, deren Quellen benutzerdefinierte Assemblyattribute enthalten. Beim Erstellen eines Assemblymanifests aus mindestens einer NETMODULE-Datei, die Verweise auf diese Typen enthält, verwendet ALink die zu diesen Verweisen gehörenden Informationen, um echte benutzerdefinierte Attribute auszugeben. Daher wird dieser Typ nie instanziiert, und Verweise auf diesen Typ werden nur als Teil des Buildprozesses verwendet und erfüllen in der endgültigen Assembly keinen Zweck.  
  
 Verweise auf diesen Typ geben benutzerdefinierte Attribute an, die nicht sicherheitsrelevant sind, aber mehrfach verwendet werden können.  
  
 Diese Typen sind in .NET Framework mit "intern" markiert und befinden sich in <xref:System.Runtime.CompilerServices>.  
  
## <a name="requirements"></a>Anforderungen  
 mscorlib.dll  
  
## <a name="see-also"></a>Siehe auch
- [AssemblyAttributesGoHere](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgohere.md)
- [AssemblyAttributesGoHereS](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheres.md)
- [AssemblyAttributesGoHereSM](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
