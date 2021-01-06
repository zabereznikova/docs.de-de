---
title: Warnung SYSLIB0010
description: In diesem Artikel erfahren Sie mehr über die veralteten Elemente, die zur Kompilierzeit die Warnung SYSLIB0010 generieren.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 289fb3f766a6e1d37bea8faec1896d20442f43f9
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596286"
---
# <a name="syslib0010-unsupported-remoting-apis"></a>SYSLIB0010: Nicht unterstützte Remoting-APIs

[.NET-Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) ist eine Legacytechnologie, und die Infrastruktur dafür ist nur im .NET Framework vorhanden. Die folgenden Remoting-APIs sind ab .NET 5.0 als veraltet markiert. Ihre Verwendung im Code ruft zur Kompilierzeit die Warnung `SYSLIB0010` hervor.

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType>

## <a name="workarounds"></a>Problemumgehung

Sie sollten unter Umständen WCF- oder HTTP-basierte REST-Dienste verwenden, um mit Objekten in anderen Anwendungen oder auf anderen Computern zu kommunizieren. Weitere Informationen finden Sie unter [In .NET Core nicht verfügbare .NET Framework-Technologien](../../porting/net-framework-tech-unavailable.md).

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>Siehe auch

- [.NET-Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))
