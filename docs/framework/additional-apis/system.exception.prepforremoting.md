---
title: Exception. prepforremoting-Methode (System)
author: mairaw
ms.author: mairaw
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 057390d64f70d3cb8eba7d4b29b94570fdca77e3
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72405897"
---
# <a name="exceptionprepforremoting-method"></a>Exception. prepforremoting-Methode

Behält die serverseitige Stapel Überwachung bei, indem Sie an die Nachricht angehängt wird, bevor die Ausnahme erneut an der Client aufrufssite ausgelöst wird.

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a>Rückgabe

<xref:System.Exception>  
Diese <xref:System.Exception>-Instanz.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `Exception.PrepForRemoting`-Methode ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System>

**Assembly:** mscorlib. dll (in "mscorlib. dll")

**.NET Framework Versionen:** Verfügbar seit 1,0.
