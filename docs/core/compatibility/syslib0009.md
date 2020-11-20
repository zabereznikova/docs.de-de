---
title: Warnung SYSLIB0009
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung SYSLIB0009 generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 47b4f595a54800370da90f61d838c665df8b6091
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439975"
---
# <a name="syslib0009-the-authenticationmanager-authenticate-and-preauthenticate-methods-are-not-supported"></a>SYSLIB0009: Die AuthenticationManager-Methoden „Authenticate“ und „PreAuthenticate“ werden nicht unterstützt

Die folgenden APIs sind ab .NET 5.0 als veraltet markiert. Die Verwendung dieser APIs ruft zur Kompilierzeit die Warnung `SYSLIB0009` hervor.

- <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType>
- <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType>

## <a name="suppress-the-warning"></a>Unterdrücken der Warnung

Wenn Sie den Code nicht ändern können, können Sie die Warnung über eine `#pragma`-Anweisung oder eine `<NoWarn>`-Projekteinstellung unterdrücken. Beispiele finden Sie unter [Unterdrücken von Warnungen](syslib-obsoletions.md#suppress-warnings).
