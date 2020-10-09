---
ms.openlocfilehash: 53860bb867522503c5cb9bd35e25fadd00a116a2
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609159"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>Geänderter Abstand für mehrzeilige ASP.NET-Textfelder (TextBox) bei Verwendung von AntiXSSEncoder

#### <a name="details"></a>Details

In .NET Framework 4.0 wurden zwischen Zeilen eines mehrzeiligen Textfelds beim Postback zusätzliche Zeilen eingefügt, wenn <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName> verwendet wird. In .NET Framework 4.5 sind diese zusätzlichen Zeilenumbrüche nicht enthalten, wenn die Web-App auf .NET Framework 4.5 ausgelegt ist.

#### <a name="suggestion"></a>Vorschlag

Beachten Sie, dass bei Web-Apps der Version 4.0, die auf .NET Framework 4.5 neu ausgelegt wurden, mehrzeilige Textfelder möglicherweise verbessert wurden, damit diese keine zusätzlichen Zeilenumbrüche mehr einfügen. Wenn dies nicht erwünscht ist, kann die App das alte Verhalten verwenden, wenn sie unter .NET Framework 4.5 ausgeführt wird, indem sie auf .NET Framework 4.0 ausgerichtet wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.5         |
| Typ    | Neuzuweisung |
