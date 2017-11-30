---
title: Was ist neu in .NET Standard
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
ms.##devlang: dotnet
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e938c009b79af3b2f36094bbb74f4d38baeeac0b
ms.sourcegitcommit: 281070dee88db86ec3bb4634d5f558d1a4e159dd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2017
---
# <a name="whats-new-in-the-net-standard"></a>Was ist neu in .NET Standard

.NET Standard ist eine formale Spezifikation, die einen mit Versionsangabe Satz von APIs definiert, der Implementierungen von .NET verfügbar sein müssen, die mit dieser Version des Standards zu erfüllen. .NET Standard ist auf Bibliotheksentwickler ausgerichtet. Eine Bibliothek, die auf eine .NET Standardversion kann auf die Implementierung einer .NET Framework, die .NET Core oder Xamarin verwendet werden, diese Version des Standards unterstützt.

Die neueste Version von .NET Standard lautet 2.0. Es ist mit dem .NET Core 2.0 SDK sowie mit Visual Studio 2017 Version 15.3 Arbeitslast .NET Core installiert.

## <a name="supported-net-implementations"></a>Unterstützte .NET Implementierungen

Der standardmäßige .NET 2.0 wird durch folgenden Implementierungen .NET unterstützt:

- .NET Core 2.0
- .NET Framework 4.6.1
- Mono 5.4
- Xamarin.iOS 10.14
- Xamarin.Mac 3.8
- Xamarin.Android 8.0
- Universelle Windows-Plattform 10.0.16299

## <a name="whats-new-in-the-net-standard-20"></a>Was ist neu in .NET Standard 2.0
 
Der standardmäßige .NET 2.0 umfasst die folgenden neuen Features:

**Ein völlig erweiterten Satz von APIs**

Bis Version 1.6 enthalten den standardmäßigen .NET eine vergleichsweise kleine Teilmenge von APIs. Zu den ausgeschlossen wurden Sie viele APIs, die häufig in .NET Framework oder Xamarin verwendet wurden. Dadurch wird die Entwicklung, komplizierter, da sie erfordert, dass Entwickler geeigneter Ersatz für vertraut APIs, finden Wenn sie entwickeln Anwendungen und Bibliotheken, die auf mehrere Implementierungen von .NET abzielen. Der standardmäßige .NET 2.0 für Kennwortfilter durch Hinzufügen von mehr als 20.000 weitere APIs, die als in standardmäßigen .NET 1.6, die die vorherige Version des Standards verfügbar waren. Eine Liste der APIs, die den standardmäßigen .NET 2.0 hinzugefügt wurden, finden Sie unter [.NET Standard 2.0 Vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md). 

Einige der Virtual Machine Additions auf dem <xref:System> Namespace in .NET 2.0-Standard enthalten:

- Unterstützung für die <xref:System.AppDomain> Klasse.
- Bessere Unterstützung für das Arbeiten mit Arrays von zusätzliche Elemente in der <xref:System.Array> Klasse.
- Bessere Unterstützung für das Arbeiten mit Attributen aus zusätzliche Elemente in der <xref:System.Attribute> Klasse.
- Eine bessere Leistung "Kalender" Support und weitere Formatierungsoptionen für <xref:System.DateTime> Werte.
- Zusätzliche <xref:System.Decimal> Rundung Funktionalität.
- Zusätzliche Funktionen in der <xref:System.Environment> Klasse.
- Erweiterte Kontrolle über die Garbage Collection durch die <xref:System.GC> Klasse.
- Erweiterte Unterstützung für den Vergleich von Zeichenfolgen, Enumeration und Normalisierung in die <xref:System.String> Klasse.
- Unterstützung für die Sommerzeit Anpassungen und Übergangszeiten in der <xref:System.TimeZoneInfo.AdjustmentRule> und <xref:System.TimeZoneInfo.TransitionTime> Klassen.
- Funktionalität in erheblich verbessert die <xref:System.Type> Klasse.
- Bessere Unterstützung für die Deserialisierung von Ausnahmeobjekten durch Hinzufügen eines Ausnahme Konstruktors mit <xref:System.Runtime.Serialization.SerializationInfo> und <xref:System.Runtime.Serialization.StreamingContext> Parameter.

**Unterstützung für .NET Framework-Bibliotheken**

Der überwiegende Teil der Bibliotheken als Ziel .NET Framework, sondern die .NET Standard. Allerdings sind die meisten Aufrufe in diesen Bibliotheken APIs, die in standardmäßigen .NET 2.0 enthalten sind. Beginnend mit .NET Standard 2.0, können Sie .NET Framework-Bibliotheken aus einer .NET Standard-Bibliothek zugreifen, mithilfe einer [Kompatibilität Shim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification). Dieser Kompatibilitätsebene ist für Entwickler transparent; Sie müssen nichts Unternehmen, um .NET Framework-Bibliotheken zu nutzen.

Die einzige Anforderung ist, dass die APIs, die von der .NET Framework-Klassenbibliothek aufgerufen in standardmäßigen .NET 2.0 enthalten sein müssen.

**Unterstützung für Visual Basic**

Sie können jetzt .NET Standardbibliotheken in Visual Basic entwickeln. Für Visual Basic-Entwickler, die mit Visual Studio 2017 Version 15.3 oder später mit der .NET Core-arbeitsauslastung installiert enthält Visual Studio nun eine Vorlage für die Klassenbibliothek von .NET Standard. Für Visual Basic-Entwickler, die andere Entwicklungstools und -Umgebungen verwenden, können Sie die [Dotnet neue](../../core/tools/dotnet-new.md) Befehl zum Erstellen eines Projekts für .NET-Standardbibliothek. Weitere Informationen finden Sie unter der [Toolunterstützung ist für .NET Standardbibliotheken](#tooling).

<a name="tooling" />**Tools zur Unterstützung für .NET-Standardbibliotheken**

Mit der Version von .NET Core 2.0 und .NET Standard 2.0, sowohl Visual Studio 2017 und [.NET Core Befehlszeilenschnittstelle (CLI)](../../core/tools/index.md) tooling-Unterstützung für das Erstellen von .NET Standardbibliotheken enthalten. 

Bei der Installation von Visual Studio mit der **.NET Core plattformübergreifende Entwicklung** arbeitsauslastung können Sie ein Klassenbibliotheksprojekt .NET Standard 2.0 erstellen, indem Sie mithilfe einer Projektvorlage, wie die folgende Abbildung zeigt. 

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![Fügen Sie neue .NET Standard-Bibliotheksprojekt hinzu.](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![Fügen Sie neue .NET Standard-Bibliotheksprojekt hinzu.](./media/std-project-vb.png)
---

Bei Verwendung der .NET Core CLI Folgendes [Dotnet neue](../../core/tools/dotnet-new.md) Befehl erstellt ein Klassenbibliotheksprojekt, das standardmäßige .NET 2.0 ausgerichtet ist.

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a>Siehe auch
[.NET Standard](../net-standard.md)
[Einführung in .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)
