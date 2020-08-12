---
title: Zustandsverwaltung
description: Lernen Sie verschiedene Ansätze zum Verwalten des Zustands in ASP.net Web Forms und blazor kennen.
author: csharpfritz
ms.author: jefritz
ms.date: 05/15/2020
ms.openlocfilehash: bac2f00330113725f09259ca31bdf857a8769f24
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062339"
---
# <a name="state-management"></a>Zustandsverwaltung

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Die Zustands Verwaltung ist ein wichtiges Konzept für Web Forms Anwendungen, das durch den Ansichts Zustand, den Sitzungszustand, den Anwendungs Zustand und die Post Back Funktionen ermöglicht wird. Diese Zustands behafteten Features des Frameworks trugen dazu bei, die für eine Anwendung erforderliche Zustands Verwaltung zu verbergen und Anwendungsentwicklern den Schwerpunkt auf die Bereitstellung ihrer Funktionalität zu geben. Mit ASP.net Core und blazor wurden einige dieser Features verschoben, und einige dieser Features wurden vollständig entfernt. In diesem Kapitel wird erläutert, wie Sie den Status verwalten und die gleichen Funktionen mit den neuen Funktionen in blazor bereitzustellen.

## <a name="request-state-management-with-viewstate"></a>Anfordern der Zustands Verwaltung mit "ViewState"

Bei der Erörterung der Zustands Verwaltung in Web Forms Anwendung stellen viele Entwickler sofort eine Vorstellung von ViewState. In Web Forms verwaltet ViewState den Status des Inhalts zwischen HTTP-Anforderungen, indem ein großer codierter TextBlock an den Browser zurückgesendet wird. Das Feld "ViewState" kann mit dem Inhalt einer Seite, die viele Elemente enthält, überlastet werden, was möglicherweise auf mehrere Megabyte aufwächst.

Mit dem blazor-Server unterhält die APP eine fortlaufende Verbindung mit dem Server. Der Status der APP, *der als Verbindung bezeichnet wird, wird*im Server Speicher gehalten, während die Verbindung als aktiv betrachtet wird. Der Status wird nur verworfen, wenn der Benutzer von der APP oder einer bestimmten Seite in der APP weg navigiert. Alle Mitglieder der aktiven Komponenten sind zwischen Interaktionen mit dem Server verfügbar.

Dieses Feature bietet mehrere Vorteile:

- Der Komponenten Status ist sofort verfügbar und wird zwischen Interaktionen nicht neu erstellt.
- Der Status wird nicht an den Browser übermittelt.

Allerdings gibt es einige Nachteile der Persistenz im Speicher des Komponenten Zustands, die beachtet werden sollten:

- Wenn der Server zwischen der Anforderung neu gestartet wird, geht der Status verloren.
- Die Lösung für den Lastenausgleich des Anwendungs Webservers muss persistente Sitzungen enthalten, um sicherzustellen, dass alle Anforderungen desselben Browsers an denselben Server zurückgegeben werden. Wenn eine Anforderung an einen anderen Server weitergeleitet wird, geht der Status verloren.
- Die Persistenz des Komponenten Status auf dem Server kann zu ungenügendem Arbeitsspeicher auf dem Webserver führen.

Verlassen Sie sich aus den vorangehenden Gründen nicht darauf, dass sich der Zustand der Komponente auf dem Server im Arbeitsspeicher befindet. Die Anwendung sollte auch einen Sicherungsdaten Speicher für Daten zwischen Anforderungen enthalten. Einige einfache Beispiele für diese Strategie:

- Bewahren Sie in einer Einkaufswagen Anwendung den Inhalt der neuen Elemente auf, die dem Warenkorb in einem Datenbankdaten Satz hinzugefügt werden. Wenn der Status auf dem Server verloren geht, können Sie ihn aus den Datenbankdaten Sätzen wiederherstellen.
- In einem mehrteiligen Webformular erwarten Ihre Benutzer, dass Ihre Anwendung Werte zwischen den einzelnen Anforderungen speichert. Schreiben Sie die Daten zwischen den einzelnen Beiträgen Ihres Benutzers in einen Datenspeicher, sodass Sie abgerufen und in der endgültigen Form Antwort Struktur zusammengefasst werden können, wenn das mehrteilige Formular abgeschlossen ist.

Weitere Informationen zum Verwalten des Zustands in blazor-apps finden Sie unter [ASP.net Core blazor State Management](/aspnet/core/blazor/state-management).

## <a name="maintain-state-with-session"></a>Status mit Sitzung beibehalten

Web Forms Entwickler können Informationen über den aktuell aktiven Benutzer mit dem <xref:Microsoft.AspNetCore.Http.ISession?displayProperty=nameWithType> Dictionary-Objekt verwalten. Es ist einfach genug, dem ein Objekt mit einem Zeichen folgen Schlüssel hinzuzufügen `Session` , und dieses Objekt wäre zu einem späteren Zeitpunkt während der Interaktion des Benutzers mit der Anwendung verfügbar. Bei dem Versuch, die Interaktion mit http zu vermeiden, machte das-Objekt die Verwaltung des `Session` Zustands leicht.

Die Signatur des .NET Framework `Session` Objekts ist nicht mit dem ASP.net Core Objekt identisch `Session` . Sehen Sie sich [die Dokumentation für die neue ASP.net Core Sitzung](/dotnet/api/microsoft.aspnetcore.http.isession) an, bevor Sie sich für die Migration und die Verwendung des neuen Sitzungs Zustands Features entscheiden.

Die Sitzung ist in ASP.net Core-und blazor-Server verfügbar, wird jedoch nicht von der Verwendung unterbunden, um Daten in einem Datenrepository entsprechend zu speichern. Der Sitzungszustand ist auch nicht funktionsfähig, wenn Besucher die Verwendung von HTTP-Cookies in Ihrer Anwendung aufgrund von Datenschutzbedenken ablehnen.

Die Konfiguration für ASP.net Core und den Sitzungszustand ist im [Artikel Sitzungs-und Zustands Verwaltung in ASP.net Core](/aspnet/core/fundamentals/app-state#session-state)verfügbar.

## <a name="application-state"></a>Status der Anwendung

Das `Application` -Objekt im Web Forms Framework stellt ein riesiges, Anforderungs übergreifendes Repository für die Interaktion mit der Konfiguration und dem Zustand des Anwendungsbereichs bereit. Der Anwendungs Zustand war ein idealer Ort zum Speichern verschiedener Anwendungs Konfigurations Eigenschaften, auf die von allen Anforderungen verwiesen wird, unabhängig vom Benutzer, der die Anforderung sendet. Das Problem mit dem `Application` Objekt war, dass Daten nicht über mehrere Server hinweg persistent gespeichert wurden. Der Status des Anwendungs Objekts wurde zwischen Neustarts getrennt.

Wie bei `Session` wird empfohlen, dass Daten in einen permanenten Sicherungs Speicher verschoben werden, auf den mehrere Server Instanzen zugreifen können. Wenn flüchtige Daten vorhanden sind, auf die Sie über Anforderungen und Benutzer zugreifen können, können Sie Sie problemlos in einem Singleton-Dienst speichern, der in Komponenten eingefügt werden kann, die diese Informationen oder Interaktionen benötigen.

Die Erstellung eines Objekts, um den Anwendungs Zustand und seinen Verbrauch aufrechtzuerhalten, könnte der folgenden Implementierung ähneln:

```csharp
public class MyApplicationState
{
    public int VisitorCounter { get; private set; } = 0;

    public void IncrementCounter() => VisitorCounter += 1;
}
```

```csharp
app.AddSingleton<MyApplicationState>();
```

```razor
@inject MyApplicationState AppState

<label>Total Visitors: @AppState.VisitorCounter</label>
```

Das `MyApplicationState` Objekt wird nur einmal auf dem Server erstellt, und der Wert `VisitorCounter` wird abgerufen und in der Bezeichnung der Komponente ausgegeben. Der `VisitorCounter` Wert sollte persistent gespeichert und aus einem Sicherungsdaten Speicher abgerufen werden, um Dauerhaftigkeit und Skalierbarkeit zu gewährleisten.

## <a name="in-the-browser"></a>Im Browser

Anwendungsdaten können auch auf der Clientseite auf dem Gerät des Benutzers gespeichert werden, sodass Sie später verfügbar ist. Es gibt zwei Browserfunktionen, die die Persistenz von Daten in verschiedenen Bereichen des Browsers des Benutzers ermöglichen:

- `localStorage`: der Bereich des gesamten Browsers des Benutzers. Wenn die Seite erneut geladen wird, wird der Browser geschlossen und erneut geöffnet, oder eine andere Registerkarte mit derselben URL wird `localStorage` vom Browser bereitgestellt.
- `sessionStorage`-Bereich der aktuellen Browser Registerkarte des Benutzers. Wenn die Registerkarte erneut geladen wird, bleibt der Zustand erhalten. Wenn der Benutzer jedoch eine weitere Registerkarte für die Anwendung öffnet oder den Browser schließt und erneut öffnet, geht der Status verloren.

Sie können benutzerdefinierten JavaScript-Code schreiben, um mit diesen Features zu interagieren, oder es gibt eine Reihe von nuget-Paketen, die Sie verwenden können, um diese Funktionalität bereitzustellen. Eines dieser Pakete ist [Microsoft. aspnetcore. protectedbrowserstorage](https://www.nuget.org/packages/Microsoft.AspNetCore.ProtectedBrowserStorage).

Anweisungen zur Verwendung dieses Pakets für die Interaktion mit `localStorage` und `sessionStorage` finden Sie im Artikel [blazor State Management (blazor State Management](/aspnet/core/blazor/state-management#protected-browser-storage-experimental-package) ).

>[!div class="step-by-step"]
>[Zurück](pages-routing-layouts.md)
>[Weiter](forms-validation.md)
