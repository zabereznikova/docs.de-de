---
ms.openlocfilehash: 38c774417fc94fa080bf2b82c04d575e9068cdcb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858373"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>Reflection-Objekte können nicht mehr von verwaltetem Code an prozessexterne DCOM-Clients übergeben werden

|   |   |
|---|---|
|Details|Reflection-Objekte können nicht mehr von verwaltetem Code an prozessexterne DCOM-Clients übergeben werden. Die folgenden Typen sind betroffen:<ul><li><xref:System.Reflection.Assembly?displayProperty=name></li><li><xref:System.Reflection.MemberInfo?displayProperty=name> (und die abgeleiteten Typen, einschließlich <xref:System.Reflection.FieldInfo?displayProperty=name>, <xref:System.Reflection.MethodInfo?displayProperty=name>, <xref:System.Type?displayProperty=name> und <xref:System.Reflection.TypeInfo?displayProperty=name>)</li><li><xref:System.Reflection.MethodBody?displayProperty=name></li><li><xref:System.Reflection.Module?displayProperty=name></li><li><xref:System.Reflection.ParameterInfo?displayProperty=name>.</li></ul>Aufrufe von <code>IMarshal</code> für das Objekt geben <code>E_NOINTERFACE</code> zurück.|
|Vorschlag|Aktualisieren Sie den Marshallingcode, damit dieser mit Nicht-Reflection-Objekten arbeitet.|
|`Scope`|Nebenversion|
|Version|4.6|
|Geben Sie Folgendes ein:|Laufzeit|
