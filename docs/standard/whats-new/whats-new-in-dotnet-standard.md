---
title: Neuerungen im .NET Standard
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3a5833bdfcf1e3433ea82403908e9a06a88cde27
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="whats-new-in-the-net-standard"></a>Neuerungen im .NET Standard

Der .NET Standard ist eine formale Spezifikation. Sie definiert einen Satz von APIs mit Versionsangabe, die in .NET Implementierungen verfügbar sein müssen, die dieser Version des Standards entsprechen. .NET Standard ist auf Bibliotheksentwickler ausgerichtet. Eine Bibliothek, die auf eine .NET Standard-Version abzielt, kann in jeder .NET Framework-, .NET Core- oder Xamarin-Implementierung verwendet werden, die diese Version des Standards unterstützt.

Die neueste Version von .NET Standard ist 2.0. Diese Version ist im .NET Core 2.0 SDK und in der Visual Studio 2017-Version 15.3 mit installierter .NET Core-Workload enthalten.

## <a name="supported-net-implementations"></a>Unterstützte .NET-Implementierungen

Der .NET Standard 2.0 wird von den folgenden .NET-Implementierungen unterstützt:

- .NET Core 2.0
- .NET Framework 4.6.1
- Mono 5.4
- Xamarin.iOS 10.14
- Xamarin.Mac 3.8
- Xamarin.Android 8.0
- Universelle Windows-Plattform 10.0.16299

## <a name="whats-new-in-the-net-standard-20"></a>Neuerungen im .NET Standard 2.0
 
Der .NET Standard 2.0 umfasst folgende neue Features:

**Ein umfassend erweiterter Satz von APIs**

Bis einschließlich Version 1.6 enthielt der .NET Standard eine vergleichsweise kleine Teilmenge von APIs. Nicht enthalten war eine Vielzahl von APIs, die im Allgemeinen in .NET Framework oder Xamarin verwendet wurden. Dies verkompliziert die Entwicklung, da Entwickler geeigneten Ersatz für vertraute APIs finden müssen, wenn sie Anwendungen und Bibliotheken für verschiedene .NET-Implementierungen erstellen. Im .NET Standard 2.0 besteht diese Einschränkung nicht mehr, da über 20.000 weitere APIs hinzugefügt wurden, als im .NET Standard 1.6, der vorherigen Version des Standards, verfügbar waren. Eine Liste der APIs, die zum .NET Standard 2.0, hinzugefügt wurden, finden Sie unter [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md). 

Im Folgenden finden Sie einige der neuen Features für den <xref:System>-Namespace im .NET Standard 2.0:

- Unterstützung für die <xref:System.AppDomain>-Klasse.
- Bessere Unterstützung für die Arbeit mit Arrays dank zusätzlicher Member in der <xref:System.Array>-Klasse.
- Bessere Unterstützung für die Arbeit mit Attributen dank zusätzlicher Member in der <xref:System.Attribute>-Klasse.
- Bessere Kalenderunterstützung und zusätzliche Formatierungsoptionen für <xref:System.DateTime>-Werte.
- Zusätzliche <xref:System.Decimal>-Rundungsfunktionen.
- Zusätzliche Funktionen in der <xref:System.Environment>-Klasse.
- Erweiterte Steuerung des Garbage Collector über die <xref:System.GC>-Klasse.
- Erweiterte Unterstützung für Zeichenfolgenvergleich, Enumeration und Normalisierung in der <xref:System.String>-Klasse.
- Unterstützung für Sommerzeitanpassungen und Übergangszeiten in den Klassen <xref:System.TimeZoneInfo.AdjustmentRule> und <xref:System.TimeZoneInfo.TransitionTime>.
- Erheblich erweiterte Funktionalität in der <xref:System.Type>-Klasse.
- Bessere Unterstützung für die Deserialisierung von Ausnahmeobjekten durch Hinzufügen eines Ausnahmekonstruktors mit den Parametern <xref:System.Runtime.Serialization.SerializationInfo> und <xref:System.Runtime.Serialization.StreamingContext>.

**Unterstützung für .NET Framework-Bibliotheken**

Die überwiegende Mehrheit von Bibliotheken wird eher für das .NET Framework als für den .NET Standard entworfen. Die meisten Aufrufe in diesen Bibliotheken gelten jedoch für APIs, die im .NET Standard 2.0 enthalten sind. Ab .NET Standard 2.0 können Sie mithilfe eines [Kompatibilitätsshims](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification) von einer .NET Standard-Bibliothek auf .NET Framework-Bibliotheken zugreifen. Diese Kompatibilitätsebene ist transparent für Entwickler – Sie müssen keine besondere Maßnahme ergreifen, um von .NET Framework-Bibliotheken zu profitieren.

Die einzige Anforderung besteht darin, dass die von der .NET Framework-Klassenbibliothek aufgerufenen APIs im .NET Standard 2.0 enthalten sein müssen.

**Unterstützung für Visual Basic**

Sie können jetzt .NET Standard-Bibliotheken in Visual Basic entwickeln. Für Visual Basic-Entwickler, die Visual Studio 2017 Version 15.3 oder höher mit installierter .NET Core-Workload verwenden, enthält Visual Studio jetzt eine Vorlage für die .NET Standard-Klassenbibliothek. Visual Basic-Entwickler, die andere Entwicklungstools und -umgebungen verwenden, können den Befehl [dotnet new](../../core/tools/dotnet-new.md) verwenden, um ein Projekt für die .NET Standard-Bibliothek zu erstellen. Weitere Informationen finden Sie unter [Toolunterstützung für .NET Standard-Bibliotheken](#tooling).

<a name="tooling" />**Toolunterstützung für .NET Standard-Bibliotheken**

Mit der Veröffentlichung von .NET Core 2.0 und .NET Standard 2.0 enthalten sowohl Visual Studio 2017 als auch die [.NET Core-Befehlszeilenschnittstelle (CLI)](../../core/tools/index.md) Toolunterstützung für die Erstellung von .NET Standard-Bibliotheken. 

Wenn Sie Visual Studio mit der Workload für die **plattformübergreifende .NET Core-Entwicklung** installieren, können Sie ein .NET Standard 2.0-Bibliotheksprojekt mithilfe einer Projektvorlage erstellen, wie in der folgenden Abbildung veranschaulicht. 

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![Hinzufügen eines .NET Standard-Bibliotheksprojekts](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![Hinzufügen eines .NET Standard-Bibliotheksprojekts](./media/std-project-vb.png)
---

Wenn Sie die .NET Core-CLI verwenden, erstellt der folgende [dotnet new](../../core/tools/dotnet-new.md)-Befehl ein Klassenbibliotheksprojekt mit .NET Standard 2.0 als Ziel.

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a>Siehe auch
[.NET Standard](../net-standard.md)
[Einführung in .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)
