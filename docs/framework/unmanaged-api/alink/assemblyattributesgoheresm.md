---
title: Assemblyattributesgoheresm-Klasse (System. Runtime. CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereSM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereSM
helpviewer_keywords:
- AssemblyAttributesGoHereSM type
- Alink API, AssemblyAttributesGoHereSM type
ms.assetid: 4cf9bf39-1527-49e0-a0e9-55e7a018bf66
topic_type:
- apiref
ms.openlocfilehash: 379ba20ebf675bec71e6e5f5bcfc0dc2fbd1f92c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446601"
---
# <a name="assemblyattributesgoheresm-class"></a>Assemblyattributesgoheresm-Klasse

Wird von ALink als Platzhalter verwendet, um Informationen über benutzerdefinierte Attribute zu speichern.

## <a name="syntax"></a>Syntax

```csharp
internal sealed class AssemblyAttributesGoHereSM
```

## <a name="remarks"></a>Hinweise

Verweise auf diesen Typ können in NETMODULE-Dateien eingebettet sein, deren Quellen benutzerdefinierte Assemblyattribute enthalten. Beim Erstellen eines Assemblymanifests aus mindestens einer NETMODULE-Datei, die Verweise auf diese Typen enthält, verwendet ALink die zu diesen Verweisen gehörenden Informationen, um echte benutzerdefinierte Attribute auszugeben. Daher wird dieser Typ nie instanziiert, und Verweise auf diesen Typ werden nur als Teil des Buildprozesses verwendet und erfüllen in der endgültigen Assembly keinen Zweck.

Verweise auf diesen Typ geben benutzerdefinierte Attribute an, die sicherheitsrelevant sind und mehrfach verwendet werden.

Diese Typen werden innerhalb des .NET Framework als "intern" gekennzeichnet und befinden sich im <xref:System.Runtime.CompilerServices>-Namespace.

## <a name="requirements"></a>Voraussetzungen

mscorlib.dll

## <a name="see-also"></a>Siehe auch

- [AssemblyAttributesGoHere](assemblyattributesgohere.md)
- [AssemblyAttributesGoHereM](assemblyattributesgoherem.md)
- [AssemblyAttributesGoHereS](assemblyattributesgoheres.md)
