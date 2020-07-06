---
ms.openlocfilehash: 150b98255b3075a8fe8cad60ce234206b788a5f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617188"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a>Der Abstand für mehrzeilige ASP.NET-Textfelder (TextBox) wurde bei der Verwendung von AntiXSSEncoder geändert

#### <a name="details"></a>Details

In .NET Framework 4.0 wurden zwischen Zeilen eines mehrzeiligen Textfelds beim Postback zusätzliche Zeilen eingefügt, wenn <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName> verwendet wird. In .NET Framework 4.5 sind diese zusätzlichen Zeilenumbrüche nicht enthalten, wenn die Web-App auf .NET Framework 4.5 ausgelegt ist.

#### <a name="suggestion"></a>Vorschlag

Beachten Sie, dass bei Web-Apps der Version 4.0, die auf .NET Framework 4.5 neu ausgelegt wurden, mehrzeilige Textfelder möglicherweise verbessert wurden, damit diese keine zusätzlichen Zeilenumbrüche mehr einfügen. Wenn dies nicht erwünscht ist, kann die App das alte Verhalten verwenden, wenn sie unter .NET Framework 4.5 ausgeführt wird, indem sie auf .NET Framework 4.0 ausgerichtet wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.5         |
| Typ    | Neuzuweisung |
