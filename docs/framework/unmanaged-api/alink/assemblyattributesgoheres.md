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
# <a name="assemblyattributesgoheres"></a>AssemblyAttributesGoHereS

Wird von ALink als Platzhalter verwendet, um Informationen über benutzerdefinierte Attribute zu speichern.

## <a name="syntax"></a>Syntax

```
internal sealed class AssemblyAttributesGoHereS
```

## <a name="remarks"></a>Hinweise

Verweise auf diesen Typ können in NETMODULE-Dateien eingebettet sein, deren Quellen benutzerdefinierte Assemblyattribute enthalten. Beim Erstellen eines Assemblymanifests aus mindestens einer NETMODULE-Datei, die Verweise auf diese Typen enthält, verwendet ALink die zu diesen Verweisen gehörenden Informationen, um echte benutzerdefinierte Attribute auszugeben. Daher wird dieser Typ nie instanziiert, und Verweise auf diesen Typ werden nur als Teil des Buildprozesses verwendet und erfüllen in der endgültigen Assembly keinen Zweck.

Verweise auf diesen Typ geben benutzerdefinierte Attribute an, die sicherheitsrelevant sind und nicht mehrfach verwendet werden.

Diese Typen sind "intern" in .NET Framework markiert, und befinden sich in der <xref:System.Runtime.CompilerServices> Namespace.

## <a name="requirements"></a>Anforderungen

mscorlib.dll

## <a name="see-also"></a>Siehe auch

- [AssemblyAttributesGoHere](assemblyattributesgohere.md)
- [AssemblyAttributesGoHereM](assemblyattributesgoherem.md)
- [AssemblyAttributesGoHereSM](assemblyattributesgoheresm.md)
