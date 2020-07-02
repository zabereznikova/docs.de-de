---
ms.openlocfilehash: 4a65e721e5639f12445a9a44f46baa0d26898a88
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615675"
---
### <a name="il-ret-not-allowed-in-a-try-region"></a>Die IL-ret-Anweisung ist in einem try-Block nicht zulässig

#### <a name="details"></a>Details

Im Gegensatz zum JIT64-Compiler lässt (in .NET Framework 4.6 verwendets) RyuJIT keine IL-ret-Anweisung in einem „try“-Block zu. Eine Rückgabe innerhalb eines try-Block ist gemäß der ECMA-335-Spezifikation nicht zulässig, und kein bekannter verwalteter Compiler generiert eine solche IL. Allerdings führt der JIT64-Compiler solche IL aus, wenn sie mithilfe von Reflektionsausgabe generiert wurde.

#### <a name="suggestion"></a>Vorschlag

Wenn eine App eine IL generiert, die einen „ret“-Opcode in einem „try“-Block enthält, kann die App auf .NET Framework 4.5 ausgelegt werden, um den alten JIT-Compiler zu verwenden und dieses Problem zu vermeiden. Alternativ kann die generierte IL aktualisiert und nach dem try-Block zurückgegeben werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.6         |
| Typ    | Neuzuweisung |
