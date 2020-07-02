---
ms.openlocfilehash: c20d5fb3d700ba7649e423a79e4598b327c50a00
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622244"
---
### <a name="incorrect-code-generation-when-passing-and-comparing-uint16-values"></a>Falsche Codegenerierung bei der Übergabe und dem Vergleich von UInt16-Werten

#### <a name="details"></a>Details

Aufgrund von Änderungen, die in .NET Framework 4.7 eingeführt wurden, vergleicht der Code, der vom JIT-Compiler generiert wird, in Anwendungen, die unter .NET Framework 4.7 ausgeführt werden, manchmal zwei <code>T:System.UInt16</code>-Werte fehlerhaft miteinander. Weitere Informationen finden Sie unter [Issue #11508: Silent bad codegen when passing and comparing ushort args (Problem #11508: Lautlose, ungültige Codegenerierung beim Übergeben und Vergleichen von ushort-Argumenten)](https://github.com/dotnet/coreclr/issues/11508) unter GitHub.com.

#### <a name="suggestion"></a>Vorschlag

Wenn Sie beim Vergleichen von unsignierten 16-Bit-Werten in .NET Framework 4.7 auf ein Problem stoßen, führen Sie ein Upgrade auf .NET Framework 4.7.1 aus.

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.7|
|Typ|Laufzeit|
