---
title: Warnung „SYSLIB0008“
description: In diesem Artikel erfahren Sie mehr über das veraltete Element, das zur Kompilierzeit die Warnung „SYSLIB0008“ generiert.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 22ac5b4c5f57ec3f92585ee8d1f8cf278a15dbb0
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440594"
---
# <a name="syslib0008-createpdbgenerator-is-not-supported"></a>SYSLIB0008: „CreatePdbGenerator“ wird nicht unterstützt.

Die API <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> ist ab .NET 5.0 als veraltet markiert. Die Verwendung dieser API ruft zur Kompilierzeit die Warnung `SYSLIB0008` hervor.

## <a name="suppress-the-warning"></a>Unterdrücken der Warnung

Wenn Sie den Code nicht ändern können, können Sie die Warnung über eine `#pragma`-Anweisung oder eine `<NoWarn>`-Projekteinstellung unterdrücken. Beispiele finden Sie unter [Unterdrücken von Warnungen](syslib-obsoletions.md#suppress-warnings).
