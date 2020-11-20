---
title: 'NETSDK1079: Das Paket „Microsoft.AspNetCore.All“ wird nicht unterstützt, wenn .NET Core 3.0 oder höher als Zielversion verwendet wird.'
description: Auflösen der Migration von Microsoft.AspNetCore.App
author: dsplaisted
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1079
ms.openlocfilehash: e0b7aba909dbd2931f755238a2de2418d294751d
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445677"
---
# <a name="netsdk1079-the-microsoftaspnetcoreall-package-is-not-supported-when-targeting-net-core-30-or-higher"></a>NETSDK1079: Das Paket „Microsoft.AspNetCore.All“ wird nicht unterstützt, wenn .NET Core 3.0 oder höher als Zielversion verwendet wird.

**Dieser Artikel gilt für:** ✔️ .NET Core SDK 3.1.100 und höher

Diese Fehlermeldung wird möglicherweise angezeigt, wenn:

- Sie ein ASP.NET Core-Projekt von .NET Core 2.2 oder früher auf .NET Core 3.0 oder höher neu zuweisen.
- das Projekt das Paket „Microsoft.AspNetCore.All“ verwendet.

Entfernen Sie `PackageReference` für Microsoft.AspNetCore.All.  Möglicherweise müssen Sie auch Paketverweise für Pakete hinzufügen, auf die von Microsoft.AspNetCore.All verwiesen wird, die aber nicht im freigegebenen ASP.NET Core-Framework enthalten sind.  Diese Pakete sind hier aufgeführt: [Migrieren von Microsoft.AspNetCore.All zu Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage#migrating-from-microsoftaspnetcoreall-to-microsoftaspnetcoreapp)

Weitere Informationen finden Sie unter [Migrieren von ASP.NET Core 2.2 zu 3.0](/aspnet/core/migration/22-to-30).
