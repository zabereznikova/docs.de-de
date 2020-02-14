---
title: Exception. prepforremoting-Methode (System)
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: ce1c24578690a1643b7f5af0e44eaae95ed7b0a2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214897"
---
# <a name="exceptionprepforremoting-method"></a>Exception.PrepForRemoting-Methode

Behält die serverseitige Stapel Überwachung bei, indem Sie an die Nachricht angehängt wird, bevor die Ausnahme erneut an der Client aufrufssite ausgelöst wird.

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a>Rückgabe

<xref:System.Exception>  
Diese <xref:System.Exception>-Instanz.

## <a name="remarks"></a>Bemerkungen

> [!WARNING]
> Die `Exception.PrepForRemoting`-Methode ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System>

**Assembly:** mscorlib. dll (in "mscorlib. dll")

**.NET Framework Versionen:** Verfügbar seit 1,0.
