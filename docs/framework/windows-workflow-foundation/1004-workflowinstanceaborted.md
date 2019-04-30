---
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d34f6f1ab6af8e06a0f28fb043faf9fe16a8b211
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008615"
---
# <a name="1004---workflowinstanceaborted"></a>1004 - WorkflowInstanceAborted

## <a name="properties"></a>Eigenschaften

|||
|-|-|
|ID|1004|
|Schlüsselwörter|WFRuntime|
|Ebene|Information|
|Kanal|Microsoft-Windows-Application Server-Applications/Debug|

## <a name="description"></a>Beschreibung

Gibt an, dass eine Workflowinstanz mit einer Ausnahme abgebrochen wurde.

## <a name="message"></a>Meldung

WorkflowInstance-ID: '%1' wurde mit einer Ausnahme abgebrochen.

## <a name="details"></a>Details

|Datenelementname|Datenelementtyp|Beschreibung|
|--------------------|--------------------|-----------------|
|WorkflowInstanceId|`xs:string`|Die Instanz-ID für den Workflow.|
|Ausnahme|`xs:string`|Die Ausnahmedetails der Ausnahme.|
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
