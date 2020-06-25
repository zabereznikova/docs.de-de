---
title: Sicheres Aktualisieren von Schnittstellen mit Standardschnittstellenmethoden in C#
description: In diesem fortgeschrittenen Tutorial wird erläutert, wie Sie vorhandenen Schnittstellendefinitionen problemlos neue Funktionen hinzufügen können, ohne alle Klassen und Strukturen zu brechen, die diese Schnittstelle implementieren.
ms.date: 05/06/2019
ms.technlogy: csharp-advanced-concepts
ms.custom: mvc
ms.openlocfilehash: 1e73f9001414631975248f1a1658833d2785169b
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803209"
---
# <a name="tutorial-update-interfaces-with-default-interface-methods-in-c-80"></a>Tutorial: Aktualisieren von Schnittstellen mit Standardschnittstellenmethoden in C# 8.0

Ab C# 8.0 können Sie in .NET Core 3.0 eine Implementierung definieren, wenn Sie einen Member einer Schnittstelle deklarieren. Das häufigste Szenario ist das sichere Hinzufügen von Membern zu einer Schnittstelle, die bereits veröffentlicht ist und von unzähligen Clients verwendet wird.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> * Erweitern Sie Schnittstellen problemlos durch Hinzufügen von Methoden mit Implementierungen.
> * Erstellen Sie parametrisierte Implementierungen, um größere Flexibilität zu bieten.
> * Ermöglichen Sie Implementierern, eine spezifischere Implementierung in Form einer Überschreibung zu bieten.

## <a name="prerequisites"></a>Voraussetzungen

Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten, einschließlich des C# 8.0-Compilers. Der C# 8.0-Compiler steht ab [Visual Studio 2019 Version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder mit dem [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) zur Verfügung.

## <a name="scenario-overview"></a>Übersicht über das Szenario

Dieses Tutorial beginnt mit Version 1 einer Kundenbeziehungsbibliothek. Sie erhalten die Startanwendung von unserem [Beispielerepository auf GitHub](https://github.com/dotnet/samples/tree/master/csharp/tutorials/default-interface-members-versions/starter/customer-relationship). Das Unternehmen, das diese Bibliothek erstellt hat, beabsichtigte, dass Kunden mit vorhandenen Anwendungen seine Bibliothek verwenden. Minimale Schnittstellendefinitionen wurden bereitgestellt, die Benutzer ihrer Bibliothek implementieren sollten. So sieht die Schnittstellendefinition für einen Kunden aus:

[!code-csharp[InitialCustomerInterface](~/samples/snippets/csharp/tutorials/default-interface-members-versions/starter/customer-relationship/ICustomer.cs?name=SnippetICustomerVersion1)]

Eine zweite Schnittstelle wurde definiert, die eine Bestellung darstellt:

[!code-csharp[InitialOrderInterface](~/samples/snippets/csharp/tutorials/default-interface-members-versions/starter/customer-relationship/IOrder.cs?name=SnippetIorderVersion1)]

Von diesen Schnittstellen aus konnte das Team eine Bibliothek für die Benutzer erstellen, um den Kunden eine bessere Benutzererfahrung zu bieten. Das Ziel bestand darin, eine intensivere Beziehung zu Bestandskunden aufzubauen und ihre Beziehungen zu neuen Kunden zu verbessern.

Jetzt ist es Zeit, die Bibliothek für das nächste Release zu aktualisieren. Eines der angeforderten Features gewährt Kunden, die viele Bestellungen aufgeben, einen Treuerabatt. Dieser neue Treuerabatt wird angewendet, wenn ein Kunde eine Bestellung aufgibt. Der spezifische Rabatt ist eine Eigenschaft jedes einzelnen Kunden. Jede Implementierung von `ICustomer` kann andere Regeln für den Treuerabatt festlegen.

Die naheliegendste Methode zum Hinzufügen dieser Funktionalität ist die Verbesserung der `ICustomer`-Schnittstelle mit einer Methode zur Anwendung eines Treuerabatts. Diese Entwurfsempfehlung löste bei erfahrenen Entwicklern Bedenken aus: „Schnittstellen sind unveränderlich, sobald sie veröffentlicht sind! Dies ist eine einschneidende Änderung!“ C# 8.0 fügt *Standardschnittstellenimplementierungen* zum Aktualisieren von Schnittstellen hinzu. Die Autoren der Bibliothek können der Schnittstelle neue Member hinzufügen und eine Standardimplementierung für diese Member bereitstellen.

Mit Implementierungen von Standardschnittstellen können Entwickler eine Schnittstelle aktualisieren, während gleichzeitig alle Implementierer diese Implementierung überschreiben können. Benutzer der Bibliothek können die standardmäßige Implementierung als eine nicht unterbrechende Änderung akzeptieren. Wenn ihre Geschäftsregeln anders sind, können sie überschreiben.

## <a name="upgrade-with-default-interface-methods"></a>Upgraden mit Standardschnittstellenmethoden

Das Team stimmte der wahrscheinlichsten Standardimplementierung zu: einem Treuerabatt für Kunden.

Das Upgrade sollte die Funktionalität zum Festlegen von zwei Eigenschaften bieten: die für den Rabatt erforderliche Anzahl an Bestellungen sowie den Prozentsatz des Rabatts. Damit wird es zum idealen Szenario für Standardschnittstellenmethoden. Sie können der `ICustomer`-Schnittstelle eine Methode hinzufügen und die wahrscheinlichste Implementierung bereitstellen. Alle vorhandenen und alle neuen Implementierungen können die Standardimplementierung verwenden oder ihre eigene angeben.

Fügen Sie zunächst die neue Methode einschließlich deren Text der Schnittstelle hinzu:

[!code-csharp[InitialOrderInterface](~/samples/snippets/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/ICustomer.cs?name=SnippetLoyaltyDiscountVersionOne)]

Der Bibliotheksautor schrieb einen ersten Test zum Überprüfen der Implementierung:

[!code-csharp[TestDefaultImplementation](~/samples/snippets/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/Program.cs?name=SnippetTestDefaultImplementation)]

Beachten Sie den folgenden Teil des Tests:

[!code-csharp[TestDefaultImplementation](~/samples/snippets/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/Program.cs?name=SnippetHighlightCast)]

Diese Umwandlung von `SampleCustomer` zu `ICustomer` ist erforderlich. Die `SampleCustomer`-Klasse muss keine Implementierung für `ComputeLoyaltyDiscount` bereitstellen; dies erfolgt über die `ICustomer`-Schnittstelle. Allerdings erbt die `SampleCustomer`-Klasse keine Member von ihren Schnittstellen. Diese Regel hat sich nicht geändert. Um jede in der Schnittstelle deklarierte und implementierte Methode aufrufen zu können, muss die Variable vom Typ der Schnittstelle sein, in diesem Beispiel `ICustomer`.

## <a name="provide-parameterization"></a>Bereitstellen der Parametrisierung

Ein guter Anfang. Aber die Standardimplementierung ist zu restriktiv. Viele Nutzer dieses Systems könnten unterschiedliche Schwellenwerte für die Anzahl der Käufe, eine andere Dauer der Mitgliedschaft oder einen anderen Rabattprozentsatz auswählen. Sie können mehr Kunden eine bessere Upgradeerfahrung bieten, indem Sie eine Möglichkeit zum Festlegen dieser Parameter bereitstellen. Wird fügen nun eine statische Methode hinzu, die diese drei, die Standardimplementierung steuernden Parameter festlegt:

[!code-csharp[VersionTwoImplementation](~/samples/snippets/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/ICustomer.cs?name=SnippetLoyaltyDiscountVersionTwo)]

Dieses kleine Codefragment zeigt viele neue Sprachfunktionen. Schnittstellen können nun statische Member einschließlich Feldern und Methoden enthalten. Verschiedene Zugriffsmodifizierer sind ebenfalls aktiviert. Die zusätzlichen Felder sind privat, die neue Methode ist öffentlich. Beliebige der Modifizierer sind auf Schnittstellenmembern erlaubt.

Anwendungen, die die allgemeine Formel zum Berechnen des Treuerabatts verwenden, aber andere Parameter, müssen keine benutzerdefinierte Implementierung bereitstellen; sie können die Argumente über eine statische Methode festlegen. Der folgende Code legt z.B. eine „Kundenwertschätzung“ fest, die jeden Kunden mit mehr als einem Monat Mitgliedschaft belohnt:

[!code-csharp[SetLoyaltyThresholds](~/samples/snippets/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/Program.cs?name=SnippetSetLoyaltyThresholds)]

## <a name="extend-the-default-implementation"></a>Erweitern der Standardimplementierung

Der Code, den Sie bisher hinzugefügt haben, hat eine einfache Implementierung für diese Szenarien ermöglicht, in denen Benutzer etwas wie die Standardimplementierung wünschen, oder um eine unzusammenhängende Gruppe von Regeln bereitzustellen. Für ein finales Feature werden wir den Code ein wenig umgestalten, um Szenarien zu ermöglichen, in denen Benutzer die Standardimplementierung erstellen möchten.

Stellen Sie sich ein Startupunternehmen vor, das neue Kunden gewinnen möchte. Es bietet einen Preisnachlass von 50% für die erste Bestellung eines neuen Kunden. Andernfalls erhalten Bestandskunden den Standardrabatt. Der Bibliotheksautor muss die Standardimplementierung in eine `protected static`-Methode verschieben, sodass jede Klasse, die diese Schnittstelle implementiert, den Code in ihrer Implementierung wiederverwenden kann. Die Standardimplementierung des Schnittstellenmembers ruft diese freigegebene Methode ebenfalls auf:

[!code-csharp[VersionTwoImplementation](~/samples/snippets/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/ICustomer.cs?name=SnippetFinalVersion)]

In einer Implementierung einer Klasse, die diese Schnittstelle implementiert, kann die Überschreibung die statische Hilfsmethode aufrufen und diese Logik zum Bereitstellen des „Neuer Kunde“-Rabatts erweitern:

[!code-csharp[VersionTwoImplementation](~/samples/snippets/csharp/tutorials/default-interface-members-versions/finished/customer-relationship/SampleCustomer.cs?name=SnippetOverrideAndExtend)]

Den vollständigen Code finden Sie in unserem [Beispielrepository auf GitHub.](https://github.com/dotnet/samples/tree/master/csharp/tutorials/default-interface-members-versions/finished/customer-relationship) Sie erhalten die Startanwendung von unserem [Beispielerepository auf GitHub](https://github.com/dotnet/samples/tree/master/csharp/tutorials/default-interface-members-versions/starter/customer-relationship).

Diese neuen Features bedeuten, dass Schnittstellen problemlos aktualisiert werden können, wenn eine vernünftige Standardimplementierung für diese neuen Member vorhanden ist. Entwerfen Sie Schnittstellen sorgfältig, um einzelne funktionale Konzepte auszudrücken, die von mehreren Klassen implementiert werden können. Dies erleichtert das Aktualisieren dieser Schnittstellendefinitionen, wenn neue Anforderungen für diese gleichen funktionalen Konzept entdeckt werden.
