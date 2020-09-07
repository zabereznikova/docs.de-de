---
ms.openlocfilehash: 2c44c2e1658f8de556d3f7222de3fa6d4594163a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497793"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a>Die Deserialisierung von MailMessage-Objekten, die unter .NET Framework 4.5 serialisiert wurden, kann möglicherweise fehlschlagen

#### <a name="details"></a>Details

Ab .NET Framework 4.5 können <xref:System.Web.Mail.MailMessage>-Objekte keine Zeichen mehr enthalten, die keine ASCII-Zeichen sind. In .NET Framework 4 werden nur ASCII-Zeichen unterstützt. <xref:System.Web.Mail.MailMessage>-Objekte, die Zeichen enthalten, bei denen es sich nicht um ASCII-Zeichen handelt, und unter .NET Framework 4.5 oder höher serialisiert werden, können unter .NET Framework 4 nicht deserialisiert werden.

#### <a name="suggestion"></a>Vorschlag

Vergewissern Sie sich, dass Ihr Code die Behandlung von Ausnahmen umfasst, wenn Sie ein <xref:System.Web.Mail.MailMessage>-Objekt deserialisieren.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Web.Mail.MailMessage?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Web.Mail.MailMessage`

-->
