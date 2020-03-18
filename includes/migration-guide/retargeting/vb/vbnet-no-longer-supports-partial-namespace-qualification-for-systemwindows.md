---
ms.openlocfilehash: 8db115a46df3fcea103e8fa6896542d0116aa256
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804677"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>VB.NET unterstützt die Angabe partieller Namespaces für System.Windows-APIs nicht mehr

|   |   |
|---|---|
|Details|Ab .NET Framework 4.5.2 können VB.NET-Projekte keine System.Windows-APIs mit teilweise qualifizierten Namespaces angeben. Der Verweis auf <code>Windows.Forms.DialogResult</code> führt z. B. zu einem Fehler. Stattdessen muss der Code auf den vollqualifizierten Namen (<xref:System.Windows.Forms.DialogResult>) verweisen oder den bestimmten Namespace importieren und dann einfach auf <xref:System.Windows.Forms.DialogResult?displayProperty=name> verweisen.|
|Vorschlag|Der Code sollte aktualisiert werden, um auf <code>System.Windows</code>-APIs mit einfachen Namen (und den entsprechenden Namespace importieren) oder mit vollqualifizierten Namen zu verweisen.|
|`Scope`|Nebenversion|
|Version|4.5.2|
|Geben Sie Folgendes ein:|Neuzuweisung|
