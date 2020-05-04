---
title: Xamarin-Einschränkungen
ms.date: 12/13/2019
description: In diesem Artikel werden einige Einschränkungen bei der Verwendung von Xamarin beschrieben.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450405"
---
# <a name="xamarin-limitations"></a>Xamarin-Einschränkungen

Microsoft.Data.Sqlite bezieht sich auf .NET Standard 2.0 und wird unter Xamarin unterstützt. In der folgenden Tabelle sehen Sie, für welche Plattformen das SQLitePCLRaw-Standardpaket native SQLite-Binärdateien bereitstellt. Weitere Informationen zur Verwendung eines anderen Pakets oder zur Bereitstellung eigener nativer SQLite-Binärdateien finden Sie unter [Benutzerdefinierte SQLite-Versionen](custom-versions.md).

| Plattform | SQLite-Binärdateien |
| --- | --- |
| **Xamarin.Android** | — |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | ✔ |
| **Xamarin.iOS** | ✔ |
| **Xamarin.Mac** | ✔ |
| **Xamarin.TVOS** | ✔ |
| **UWP** | — |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | ✔ |

## <a name="ios"></a>iOS

Microsoft.Data.Sqlite versucht automatisch, SQLitePCLRaw-Pakete zu initialisieren. Aufgrund von Einschränkungen bei der AOT-Kompilierung (Ahead-of-Time) für Xamarin.iOS schlägt der Versuch fehl, und Sie erhalten die folgende Fehlermeldung:

> Rufen Sie `SQLitePCL.raw.SetProvider()` auf. Wenn Sie ein Bündelpaket verwenden, rufen Sie `SQLitePCL.Batteries.Init()` auf.

Fügen Sie zur Initialisierung des Pakets Ihrer App die folgende Codezeile hinzu, bevor Sie Microsoft.Data.Sqlite verwenden.

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a>Siehe auch

* [Async-Einschränkungen](async.md)
* [Benutzerdefinierte SQLite-Versionen](custom-versions.md)
