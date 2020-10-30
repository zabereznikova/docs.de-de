---
title: Warnung SYSLIB0010
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung SYSLIB0010 generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: dcd331aa5c68381ea29848bc54ee4b1a5e75330d
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333059"
---
# <a name="syslib0010-unsupported-remoting-apis"></a>SYSLIB0010: Nicht unterstützte Remoting-APIs

[.NET-Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) ist eine Legacytechnologie, und die Infrastruktur dafür ist nur im .NET Framework vorhanden. Die folgenden Remoting-APIs sind ab .NET 5.0 als veraltet markiert. Ihre Verwendung im Code ruft zur Kompilierzeit die Warnung `SYSLIB0010` hervor.

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType>

## <a name="workaround"></a>Problemumgehung

Sie sollten unter Umständen WCF- oder HTTP-basierte REST-Dienste verwenden, um mit Objekten in anderen Anwendungen oder auf anderen Computern zu kommunizieren. Weitere Informationen finden Sie unter [In .NET Core nicht verfügbare .NET Framework-Technologien](../porting/net-framework-tech-unavailable.md).

## <a name="see-also"></a>Siehe auch

- [.NET-Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))
