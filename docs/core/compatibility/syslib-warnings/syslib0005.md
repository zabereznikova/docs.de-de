---
title: Warnung „SYSLIB0005“
description: In diesem Artikel erfahren Sie mehr über das veraltete Element, das zur Kompilierzeit den Fehler „SYSLIB0005“ generiert.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 1263a4d327c735268f77ed56bdcea6a4cbed4bfa
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596321"
---
# <a name="syslib0005-the-global-assembly-cache-gac-is-not-supported"></a>SYSLIB0005: Der globale Assemblycache (GAC) wird nicht unterstützt.

.NET Core und .NET 5.0 sowie höhere Versionen verzichten auf das Konzept des globalen Assemblycaches (GAC), das in .NET Framework vorhanden war. Einige GAC-bezogene APIs werden ab .NET 5.0 als veraltet markiert, damit Entwickler zunehmend andere APIs verwenden. Die Verwendung dieser APIs ruft zur Kompilierzeit die Warnung `SYSLIB0005` hervor.

Die folgenden GAC-bezogenen APIs sind als veraltet markiert:

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType>

  Bibliotheken und Apps sollten die <xref:System.Reflection.Assembly.GlobalAssemblyCache>-API nicht beim Festlegen des Laufzeitverhaltens verwenden, da diese in .NET Core und .NET 5 (oder höher) immer `false` zurückgibt.

## <a name="workarounds"></a>Problemumgehung

Wenn die Anwendung die <xref:System.Reflection.Assembly.GlobalAssemblyCache>-Eigenschaft abfragt, sollten Sie den Aufruf entfernen. Wenn Sie den Wert <xref:System.Reflection.Assembly.GlobalAssemblyCache> verwenden, um zur Laufzeit zwischen Flows zu wählen, bei denen sich die Assembly entweder im GAC oder nicht im GAC befindet, sollten Sie sich überlegen, ob der Flow auch für eine .NET 5-Anwendung (oder höher) geeignet ist.

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>Siehe auch

- [Globaler Assemblycache](../../../framework/app-domains/gac.md)
