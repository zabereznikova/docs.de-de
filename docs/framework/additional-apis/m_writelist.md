---
title: Connection.m_WriteList Field
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
author: guardrex
ms.author: mairaw
ms.openlocfilehash: a7446b9cbbfd4d3a4d38368a8e24c99527cf9108
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705934"
---
# <a name="connectionmwritelist-field"></a>Connection.m\_WriteList-Feld

`Connection.m_WriteList` ist ein <xref:System.Collections.ArrayList> von <xref:System.Net.HttpWebRequest> Objekte, die in der Warteschlange befinden, die über HTTP gesendet werden.

## <a name="syntax"></a>Syntax
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> Die `Connection.m_WriteList` Feld privat ist und nicht direkt in Ihrem Code verwendet werden soll.
> 
> Microsoft unterstützt nicht die Verwendung dieses Felds in einer produktionsanwendung unter keinen Umständen.

## <a name="requirements"></a>Anforderungen

**Namespace:** <xref:System.Net>

**Assembly:** System (in "System.dll")

**.NET Framework-Versionen:** Verfügbar seit 2.0.
