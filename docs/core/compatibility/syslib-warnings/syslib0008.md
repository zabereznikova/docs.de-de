---
title: Warnung „SYSLIB0008“
description: In diesem Artikel erfahren Sie mehr über das veraltete Element, das zur Kompilierzeit die Warnung „SYSLIB0008“ generiert.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 2b573f4b28cdf79107395f5cb38a4226d0ccc11e
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596285"
---
# <a name="syslib0008-createpdbgenerator-is-not-supported"></a>SYSLIB0008: „CreatePdbGenerator“ wird nicht unterstützt.

Die API <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> ist ab .NET 5.0 als veraltet markiert. Die Verwendung dieser API ruft zur Kompilierzeit die Warnung `SYSLIB0008` hervor.

## <a name="suppress-the-warning"></a>Unterdrücken der Warnung

Wenn Sie den Code nicht ändern können, können Sie die Warnung über eine `#pragma`-Anweisung oder eine `<NoWarn>`-Projekteinstellung unterdrücken. Beispiele finden Sie unter [Unterdrücken von Warnungen](../syslib-obsoletions.md#suppress-warnings).
