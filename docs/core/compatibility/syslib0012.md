---
title: Warnung SYSLIB0012
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung SYSLIB0012 generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 2ed93b6eefbaa861faca319f0cc9bf19ac741f3b
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333057"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a>SYSLIB0012: Assembly.CodeBase und Assembly.EscapedCodeBase sind veraltet

Die folgenden APIs sind ab .NET 5.0 als veraltet markiert. Ihre Verwendung im Code ruft zur Kompilierzeit die Warnung `SYSLIB0012` hervor.

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

Problemumgehung

Verwenden Sie stattdessen <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>.
