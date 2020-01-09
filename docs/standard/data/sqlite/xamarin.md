---
title: Xamarin-Einschränkungen
ms.date: 12/13/2019
description: Beschreibt einige der Einschränkungen, die bei der Verwendung von xamarin auftreten werden.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450405"
---
# <a name="xamarin-limitations"></a>Xamarin-Einschränkungen

"Microsoft. Data. sqlite" ist .NET Standard 2,0 und wird für xamarin unterstützt. In der folgenden Tabelle ist aufgeführt, für welche Plattformen das sqlitepclraw-Standardpaket Native SQLite-Binärdateien bereitstellt. Weitere Informationen zur Verwendung eines anderen Pakets oder zum Bereitstellen eigener Binärdateien für SQLite finden Sie unter [benutzerdefinierte SQLite-Versionen](custom-versions.md) .

| Platform | SQLite-Binärdateien |
| --- | --- |
| **Xamarin.Android** | — |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | ✔ |
| **Xamarin.iOS** | ✔ |
| **Xamarin.Mac** | ✔ |
| **Xamarin. tvos** | ✔ |
| **UWP** | — |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | ✔ |

## <a name="ios"></a>iOS

Microsoft. Data. sqlite versucht, sqlitepclraw-Bündel automatisch zu initialisieren. Aufgrund von Einschränkungen bei der Ahead-of-Time-Kompilierung (AOT) für xamarin. IOS schlägt der Versuch fehl, und Sie erhalten die folgende Fehlermeldung.

> Sie müssen `SQLitePCL.raw.SetProvider()`abrufen. Wenn Sie ein Paket Paket verwenden, erfolgt dies durch Aufrufen von `SQLitePCL.Batteries.Init()`.

Fügen Sie der APP vor der Verwendung von "Microsoft. Data. sqlite" die folgende Codezeile hinzu, um das Paket zu initialisieren.

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a>Siehe auch

* [Async-Einschränkungen](async.md)
* [Benutzerdefinierte SQLite-Versionen](custom-versions.md)
