---
title: AssemblyAttributesGoHere
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyAttributesGoHere
api_location: alink.dll
api_type: COM
f1_keywords: AssemblyAttributesGoHere
helpviewer_keywords:
- AssemblyAttributesGoHere type
- Alink API, AssemblyAttributesGoHere type
ms.assetid: 7b26fcb6-94f4-4f09-933e-b33efe451f4f
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3363ac5bd53688cfaa667a57afce17b6b52b1f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyattributesgohere"></a>AssemblyAttributesGoHere
Wird von ALink als Platzhalter verwendet, um Informationen über benutzerdefinierte Attribute zu speichern.  
  
## <a name="syntax"></a>Syntax  
  
```  
AssemblyAttributesGoHere  
```  
  
## <a name="remarks"></a>Hinweise  
 Verweise auf diesen Typ können in NETMODULE-Dateien eingebettet sein, deren Quellen benutzerdefinierte Assemblyattribute enthalten. Beim Erstellen eines Assemblymanifests aus mindestens einer NETMODULE-Datei, die Verweise auf diese Typen enthält, verwendet ALink die zu diesen Verweisen gehörenden Informationen, um echte benutzerdefinierte Attribute auszugeben. Daher wird dieser Typ nie instanziiert, und Verweise auf diesen Typ werden nur als Teil des Buildprozesses verwendet und erfüllen in der endgültigen Assembly keinen Zweck.  
  
 Verweise auf diesen Typ geben benutzerdefinierte Attribute an, die nicht sicherheitsrelevant sind und nicht mehrfach verwendet werden.  
  
 Diese Typen sind in .NET Framework mit "intern" markiert und befinden sich in <xref:System.Runtime.CompilerServices>.  
  
## <a name="requirements"></a>Anforderungen  
 mscorlib.dll  
  
## <a name="see-also"></a>Siehe auch  
 [AssemblyAttributesGoHereM](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)  
 [AssemblyAttributesGoHereS](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheres.md)  
 [AssemblyAttributesGoHereSM](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
