---
title: Exception. prepforremoting-Methode (System)
description: Überprüfen Sie die Exception. prepforremoting-Methode in .net. Die-Methode fügt der Nachricht die serverseitige Stapel Überwachung hinzu, bevor die Ausnahme erneut auf dem Client ausgelöst wird.
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 9ceb73499ae3bb308975e6db5b961bfe40165ba3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105267"
---
# <a name="exceptionprepforremoting-method"></a>Exception.PrepForRemoting-Methode

Behält die serverseitige Stapel Überwachung bei, indem Sie an die Nachricht angehängt wird, bevor die Ausnahme erneut an der Client aufrufssite ausgelöst wird.

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a>Rückgabe

<xref:System.Exception>  
Diese <xref:System.Exception>-Instanz.

## <a name="remarks"></a>Hinweise

> [!WARNING]
> Die `Exception.PrepForRemoting` Methode ist intern und sollte nicht direkt im Code verwendet werden.
>
> Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** <xref:System>

**Assembly:** mscorlib.dll (in mscorlib.dll)

**.NET Framework Versionen:** Verfügbar seit 1,0.
