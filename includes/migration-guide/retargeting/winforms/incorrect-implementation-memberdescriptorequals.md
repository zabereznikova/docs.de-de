---
ms.openlocfilehash: 2d0798917b639bc90bf3f78f6fb9f19d0eaf2c71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614541"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a>Falsche Implementierung von MemberDescriptor.Equals

#### <a name="details"></a>Details

Die ursprüngliche Implementierung der <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>-Methode hat zwei verschiedene Zeichenfolgeneigenschaften der zu vergleichenden Objekte miteinander verglichen: den Kategorienamen und die Beschreibungszeichenfolge. Die Korrektur besteht darin, <xref:System.ComponentModel.MemberDescriptor.Category> des ersten Objekts mit <xref:System.ComponentModel.MemberDescriptor.Category> des zweiten Objekts und <xref:System.ComponentModel.MemberDescriptor.Description> des ersten Objekts mit <xref:System.ComponentModel.MemberDescriptor.Description> des zweiten Objekts zu vergleichen.

#### <a name="suggestion"></a>Vorschlag

Wenn Ihre Anwendung erfordert, dass <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> manchmal `false` zurückgibt, wenn Deskriptoren äquivalent sind, und sie als Zielplattform .NET Framework 4.6.2 verwendet, sind mehrere Optionen verfügbar:

- Nehmen Sie Codeänderungen vor, um die <xref:System.ComponentModel.MemberDescriptor.Category>- und <xref:System.ComponentModel.MemberDescriptor.Description>-Felder manuell zusätzlich zum Aufrufen der <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>-Methode zu vergleichen.
- Sie können diese Änderung deaktivieren, indem Sie der Datei „app.config“ den folgenden Wert hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />
</runtime>
```

Wenn Ihre Anwendung für .NET Framework 4.6.1 oder frühere Versionen konzipiert ist, unter .NET Framework 4.6.2 ausgeführt wird und Sie diese Änderung aktivieren möchten, können Sie den Kompatibilitätsschalter auf `false` festlegen, indem Sie der Datei „app.config“ den folgenden Wert hinzufügen:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false" />
</runtime>
```

| Name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.6.2       |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType>
