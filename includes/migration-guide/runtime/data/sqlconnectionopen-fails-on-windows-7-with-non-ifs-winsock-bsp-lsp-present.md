---
ms.openlocfilehash: a1db9916c69c5974191eb6108fb54a0d9ff060d2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622038"
---
### <a name="sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>SqlConnection.Open schlägt unter Windows 7 mit vorhandenem Nicht-IFS-Winsock-BSP oder -LSP fehl

#### <a name="details"></a>Details

Auf einem Windows 7-Computer mit einem Nicht-IFS-Winsock-BSP oder -LSP schlagen <xref:System.Data.SqlClient.SqlConnection.Open> und <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> in .NET Framework 4.5 fehl. Verwenden Sie den Befehl <code>netsh WinSock Show Catalog</code>, und untersuchen Sie alle <code>Winsock Catalog Provider Entry</code>-Elemente, die zurückgegeben werden, um zu erkennen, ob ein Nicht-IFS-Winsock-BSP oder -LSP installiert ist. Wenn für den Servicekennzeichenwert das <code>0x20000</code>-Bit gesetzt ist, verwendet der Anbieter IFS-Handle und funktioniert daher ordnungsgemäß. Wenn das <code>0x20000</code>-Bit leer (nicht festgelegt) ist, handelt es sich um ein Nicht-IFS-BSP oder -LSP.

#### <a name="suggestion"></a>Vorschlag

Dieses Problem wurde in .NET Framework 4.5.2 behoben, daher kann es durch ein Upgrade von .NET Framework vermieden werden. Alternativ kann es durch Entfernen aller installierten Nicht-IFS-Winsock-LSPs vermieden werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)?displayProperty=nameWithType></li></ul>|
