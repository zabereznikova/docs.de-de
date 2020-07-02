---
ms.openlocfilehash: a54b17b2002bd0f85b8b47c5e37e040470d6c494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621330"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>Reflection-Objekte können nicht mehr von verwaltetem Code an prozessexterne DCOM-Clients übergeben werden

#### <a name="details"></a>Details

Reflection-Objekte können nicht mehr von verwaltetem Code an prozessexterne DCOM-Clients übergeben werden. Die folgenden Typen sind betroffen:<ul><li><xref:System.Reflection.Assembly?displayProperty=fullName></li><li><xref:System.Reflection.MemberInfo?displayProperty=fullName> (und die abgeleiteten Typen, einschließlich <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName> und <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</li><li><xref:System.Reflection.MethodBody?displayProperty=fullName></li><li><xref:System.Reflection.Module?displayProperty=fullName></li><li><xref:System.Reflection.ParameterInfo?displayProperty=fullName></li></ul>Aufrufe von <code>IMarshal</code> für das Objekt geben <code>E_NOINTERFACE</code> zurück.

#### <a name="suggestion"></a>Vorschlag

Aktualisieren Sie den Marshallingcode, damit dieser mit Nicht-Reflection-Objekten arbeitet.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.6|
|Typ|Laufzeit|
