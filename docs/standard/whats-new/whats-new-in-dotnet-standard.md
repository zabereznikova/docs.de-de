---
title: Neuerungen in .NET Standard
description: In diesem Artikel werden neue Features und Verbesserungen zusammengefasst, die in jeder neuen Version von .NET Standard auffindbar sind.
ms.custom: updateeachrelease
ms.date: 04/12/2018
ms.prod: dotnet-whatsnew
ms.openlocfilehash: 299477a7375381fa7f8064562e2a68e221944a05
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817173"
---
# <a name="whats-new-in-net-standard"></a>Neuerungen in .NET Standard

.NET Standard ist eine formale Spezifikation, die mehrere APIs mit Versionsangabe definiert, die in .NET-Implementierungen verfügbar sein müssen, die dieser Version des Standards entsprechen. .NET Standard ist auf Bibliotheksentwickler ausgerichtet. Eine Bibliothek, die auf eine .NET Standard-Version abzielt, kann in jeder .NET Framework-, .NET Core- oder Xamarin-Implementierung verwendet werden, die diese Version des Standards unterstützt.

.NET Standard ist in .NET Core SDK und auch in Visual Studio enthalten, wenn Sie die .NET Core-Workload wählen.

## <a name="supported-net-implementations"></a>Unterstützte .NET-Implementierungen

.NET Standard 2.0 wird von den folgenden .NET-Implementierungen unterstützt:

- .NET Core 2.0 oder höher
- .NET Framework 4.6.1 oder höher
- Mono 5.4 oder höher
- Xamarin.iOS 10.14 oder höher
- Xamarin.Mac 3.8 oder höher
- Xamarin.Android 8.0 oder höher
- Universal Windows Platform 10.0.16299 oder höher

## <a name="whats-new-in-net-standard-20"></a>Neuerungen in .NET Standard 2.0

.NET Standard 2.0 umfasst folgende neue Features:

### <a name="a-vastly-expanded-set-of-apis"></a>Ein umfassend erweiterter Satz von APIs

Bis einschließlich Version 1.6 enthielt .NET Standard eine vergleichsweise kleine Teilmenge von APIs. Nicht enthalten war eine Vielzahl von APIs, die häufig in .NET Framework oder Xamarin verwendet wurden. Dies verkompliziert die Entwicklung, da Entwickler geeigneten Ersatz für vertraute APIs finden müssen, wenn sie Anwendungen und Bibliotheken für verschiedene .NET-Implementierungen erstellen. In .NET Standard 2.0 besteht diese Einschränkung nicht mehr, da über 20.000 mehr APIs hinzugefügt wurden, als in .NET Standard 1.6, der vorherigen Version, verfügbar waren. Eine Liste der APIs, die zu .NET Standard 2.0 hinzugefügt wurden, finden Sie unter [.NET Standard 2.0 vs. 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).

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

### <a name="support-for-net-framework-libraries"></a>Unterstützung für .NET Framework-Bibliotheken

Viele Bibliotheken haben .NET Framework statt .NET Standard als Ziel. Die meisten Aufrufe in diesen Bibliotheken gelten jedoch für APIs, die in .NET Standard 2.0 enthalten sind. Ab .NET Standard 2.0 können Sie mithilfe eines [Kompatibilitätsshims](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification) von einer .NET Standard-Bibliothek auf .NET Framework-Bibliotheken zugreifen. Diese Kompatibilitätsebene ist transparent für Entwickler – Sie müssen keine besondere Maßnahme ergreifen, um von .NET Framework-Bibliotheken zu profitieren.

Die einzige Anforderung besteht darin, dass die von der .NET Framework-Klassenbibliothek aufgerufenen APIs in .NET Standard 2.0 enthalten sein müssen.

### <a name="support-for-visual-basic"></a>Unterstützung für Visual Basic

Sie können jetzt .NET Standard-Bibliotheken in Visual Basic entwickeln. Visual Studio 2019 und Visual Studio 2017, Version 15.3 oder höher, mit installierter .NET Core-Workload enthalten jetzt eine Vorlage für die .NET Standard-Klassenbibliothek. Visual Basic-Entwickler, die andere Entwicklungstools und -umgebungen verwenden, können den Befehl [dotnet new](../../core/tools/dotnet-new.md) verwenden, um ein Projekt für die .NET Standard-Bibliothek zu erstellen. Weitere Informationen finden Sie unter [Toolunterstützung für .NET Standard-Bibliotheken](#tooling-support-for-net-standard-libraries).

### <a name="tooling-support-for-net-standard-libraries"></a>Toolunterstützung für .NET Standard-Bibliotheken

Mit der Veröffentlichung von .NET Core 2.0 und .NET Standard 2.0 enthalten sowohl Visual Studio 2017 als auch die [.NET Core-CLI](../../core/tools/index.md) Toolunterstützung für die Erstellung von .NET Standard-Bibliotheken.

Wenn Sie Visual Studio mit der Workload für die **plattformübergreifende .NET Core-Entwicklung** installieren, können Sie ein .NET Standard 2.0-Bibliotheksprojekt mithilfe einer Projektvorlage wie in der folgenden Abbildung veranschaulicht erstellen:

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[C#](#tab/csharp)

![Hinzufügen eines .NET Standard-Bibliotheksprojekts](./media/std-project-cs.png)

Wenn Sie die .NET Core-CLI verwenden, erstellt der folgende [dotnet new](../../core/tools/dotnet-new.md)-Befehl ein Klassenbibliotheksprojekt für .NET Standard 2.0:

```dotnetcli
dotnet new classlib
```

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

![Hinzufügen eines .NET Standard-Bibliotheksprojekts](./media/std-project-vb.png)

Wenn Sie die .NET Core-CLI verwenden, erstellt der folgende [dotnet new](../../core/tools/dotnet-new.md)-Befehl ein Klassenbibliotheksprojekt für .NET Standard 2.0:

```dotnetcli
dotnet new classlib -lang vb
```

---

## <a name="see-also"></a>Siehe auch

- [.NET-Standard](../net-standard.md)
- [Introducing .NET Standard (Einführung in .NET Standard)](https://devblogs.microsoft.com/dotnet/introducing-net-standard/)
- [Herunterladen des .NET SDK](https://dotnet.microsoft.com/download)
