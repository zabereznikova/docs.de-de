---
ms.openlocfilehash: cef8096c971da8ae245ff974697022f350cb9195
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616059"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>VB.NET unterstützt die Angabe partieller Namespaces für System.Windows-APIs nicht mehr

#### <a name="details"></a>Details

Ab .NET Framework 4.5.2 können VB.NET-Projekte keine System.Windows-APIs mit teilweise qualifizierten Namespaces angeben. Der Verweis auf `Windows.Forms.DialogResult` führt z. B. zu einem Fehler. Stattdessen muss der Code auf den vollqualifizierten Namen (<xref:System.Windows.Forms.DialogResult>) verweisen oder den bestimmten Namespace importieren und dann einfach auf <xref:System.Windows.Forms.DialogResult?displayProperty=fullName> verweisen.

#### <a name="suggestion"></a>Vorschlag

Der Code sollte aktualisiert werden, um auf `System.Windows`-APIs mit einfachen Namen (und den entsprechenden Namespace importieren) oder mit vollqualifizierten Namen zu verweisen.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.5.2       |
| Typ    | Neuzuweisung |
