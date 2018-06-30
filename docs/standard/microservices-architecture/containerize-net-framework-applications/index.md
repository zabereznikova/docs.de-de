---
title: Migrieren von monolithischen .NET Framework-Anwendungen der Vorversion zu Windows-Containern
description: .NET-Microservices-Architektur für .NET-Containeranwendungen | Migrieren von monolithischen .NET Framework-Anwendungen der Vorversion zu Windows-Containern
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 01b84d29a559bde02ebd30535488c272d5208167
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106514"
---
# <a name="migrating-legacy-monolithic-net-framework-applications-to-windows-containers"></a>Migrieren von monolithischen .NET Framework-Anwendungen der Vorversion zu Windows-Containern

*Windows-Container können verwendet werden, um die Entwicklung und die Testumgebungen zu verbessern und um Anwendungen bereitzustellen, die auf älteren .NET Framework-Technologien wie Web* *Forms basieren. Diese Verwendung von Containern für ältere Anwendungen wird als „Lift & Shift“-Szenario bezeichnet.*

Frühere Abschnitte dieses Handbuchs haben eine Microservice-Architektur vertreten, bei der Geschäftsanwendungen über mehrere verschiedene Container verteilt werden, von denen jeder einen kleinen, fokussierten Dienst ausführt. Dieses Ziel hat viele Vorteile. Dieser Ansatz wird in der neuen Entwicklung dringend empfohlen. Unternehmenskritische Anwendungen profitieren ebenfalls genug davon, um die Kosten eines Neuentwurfs und einer Neuimplementierung zu rechtfertigen.

Es profitiert jedoch nicht jede Anwendung genug davon, um die Kosten zu rechtfertigen. Das bedeutet nicht, dass diese Anwendungen in Containerszenarios nicht verwendet werden können.

In diesem Abschnitt wird die in Abbildung 7-1 gezeigte Anwendung erläutert. Diese Anwendung wird von Enterprise-Teammitgliedern von eShopOnContainers verwendet, um den Produktkatalog anzuzeigen und zu bearbeiten.

![](./media/image1.png)

**Abbildung 7-1**. ASP.NET Web Forms-Anwendung (ältere Technologie) auf einem Windows-Container

Dabei handelt es sich um eine Web Forms-Anwendung, die zum Durchsuchen und Ändern der Katalogeinträge verwendet wird. Die Web Forms-Abhängigkeit bedeutet, dass diese Anwendung nicht auf .NET Core ausgeführt werden kann, sofern sie nicht ohne Web Forms neu geschrieben wird und stattdessen ASP.NET Core MVC verwendet. Es wird angezeigt, wie Sie solche Anwendungen ohne Änderungen in Containern ausführen können. Es wird ebenfalls angezeigt, wie Sie minimale Änderungen vornehmen können, um in einem Hybridmodus zu arbeiten, bei dem einige Funktionen in einen separaten Microservice verschoben wurden. Die meisten Funktionen bleiben jedoch in der monolithischen Anwendung.

## <a name="benefits-of-containerizing-a-monolithic-application"></a>Vorteile des Containerisierens einer monolithischen Anwendung

Die Anwendung Catalog.WebForms ist im GitHub-Repository von eShopOnContainers verfügbar (<https://github.com/dotnet/eShopOnContainers>). Bei dieser Anwendung handelt es sich um eine eigenständige Webanwendung, die auf einen hoch verfügbaren Datenspeicher zugreift. Trotzdem gibt es Vorteile bei der Ausführung der Anwendung in einem Container. Sie erstellen ein Image für die Anwendung. Ab diesem Punkt wird jede Bereitstellung in derselben Umgebung ausgeführt. Auf jedem Container wird die gleiche Version des Betriebssystems verwendet, sind die gleichen Abhängigkeiten installiert und wird das gleiche Framework verwendet. Außerdem wird jeder Container mithilfe des gleichen Prozesses erstellt. In Abbildung 7-2 wird Ihnen die in Visual Studio 2017 geladene Anwendung angezeigt.

![](./media/image2.png)

**Abbildung 7-2**. Web Forms-Anwendung für die Katalogverwaltung in Visual Studio 2017

Zusätzlich können alle Entwickler die Anwendung in dieser konsistenten Umgebung ausführen. Probleme, die nur in bestimmten Versionen auftreten, werden Entwicklern sofort angezeigt, statt in einer Staging- oder Produktionsumgebung verfügbar gemacht zu werden. Die Unterschiede zwischen den Entwicklungsumgebungen des Entwicklungsteams sind weniger wichtig, wenn die Anwendung in einem Container ausgeführt wird.

Zudem verfügen Containeranwendungen über eine flachere horizontale Skalierungskurve. Sie haben gelernt, wie Containeranwendungen mehr Container in einem virtuellen oder physischen Computer ermöglichen. Daraus ergeben sich eine höhere Dichte und weniger erforderliche Ressourcen.

Deshalb sollten sie ältere monolithische Apps in einem Docker-Container mithilfe eines „Lift & Shift“-Vorgangs ausführen. Der Ausdruck „Lift & Shift“ beschreibt den Bereich der Aufgabe: Sie heben (*Lift*) die gesamte Anwendung von einem physischen oder virtuellen Computer an und verschieben (*Shift*) diese in einen Container. Im Idealfall müssen Sie keine Änderungen am Anwendungscode vornehmen, um diese in einem Container auszuführen.

## <a name="possible-migration-paths"></a>Mögliche Migrationspfade

Die monolithische Catalog.Webforms-Anwendung ist eine Webanwendung, die sämtlichen Code enthält, einschließlich der Datenzugriffsbibliotheken. Die Datenbank wird auf einem separaten Hochverfügbarkeitscomputer ausgeführt. Diese Konfiguration wird im Beispielcode mithilfe eines Pseudokatalogdiensts simuliert: Sie können die Catalog.Webforms-Anwendung mit den gefälschten Daten ausführen, um ein reines Lift & Shift-Szenario zu simulieren. Dies zeigt den einfachsten Migrationspfad, in den Sie bestehende Objekte verschieben können, um diese ohne Änderungen im Code in einem Container auszuführen. Dieser Pfad ist für Anwendungen geeignet, die vollständig sind und minimal mit den Funktionen interagieren, die Sie in Microservices verschieben.

Die eShopOnContainers-Website greift jedoch bereits auf den Datenspeicher zu, da sie Microservices für verschiedene Szenarios verwendet. Es können zusätzlich einige kleine Änderungen am Katalog-Editor vorgenommen werden, um den Katalog-Microservice zu nutzen, statt direkt auf den Datenspeicher des Katalogs zuzugreifen.

Diese Änderungen veranschaulichen das Kontinuum für Ihre eigenen Anwendungen. Ihnen stehen alle Möglichkeiten offen: Sie können eine bestehende Anwendung ohne Änderungen in einen Container verschieben, kleine Änderungen vornehmen, um bestehenden Anwendungen den Zugriff auf neue Microservices zu ermöglichen oder eine Anwendung komplett neu schreiben, um die vollständige Teilnahme an einer neuen Architektur zu ermöglichen, die auf Microservice basiert. Der richtige Pfad hängt von den Kosten und den Vorteilen der Migration ab.

## <a name="application-tour"></a>Überblick über die Anwendung

Sie können die Projektmappe „Catalog.WebForms“ laden und die Anwendung als eigenständige Anwendung ausführen. In dieser Konfiguration verwendet die Anwendung statt einer beständigen Speicherdatenbank einen gefälschten Dienst, um Daten zurückzugeben. Die Anwendung verwendet Autofac (<https://autofac.org/>) als Inversion of Control-Container (IOC). Wenn Sie Abhängigkeitsinjektionen (DI) verwenden, können Sie die Anwendung zum Verwenden der gefälschten Daten oder des Livediensts für Katalogdaten konfigurieren. (In Kürze wird DI näher erläutert.) Der Startcode liest die Einstellung „useFake“ aus den web.config-Dateien und konfiguriert den Autofac-Container zum Einfügen des gefälschten Datendiensts oder des Livediensts für den Katalog. Wenn Sie die Anwendung ausführen und „useFake“ in der web.config-Datei auf FALSE festgelegt ist, wird Ihnen die Web Forms-Anwendung angezeigt, die die Katalogdaten darstellt.

Die meisten in dieser Anwendung verwendeten Techniken sollten jedem vertraut sein, der Web Forms bereits verwendet hat. Der Katalog-Microservice führt jedoch zwei Techniken ein, die unbekannt sein könnten: Die zuvor erwähnte Abhängigkeitsinjektion (DI) und das Arbeiten mit asynchronen Datenspeichern in Web Forms.

DI kehrt die typische objektorientierte Strategie des Schreibens von Klassen um, die alle erforderlichen Ressourcen zuordnen. Stattdessen fordern Klassen ihre Abhängigkeiten von einem Dienstcontainer an. Der Vorteil von DI ist, dass Sie externe Dienste durch Fälschungen (Mocks) ersetzen können, um das Testen oder andere Umgebungen zu unterstützen.

Der DI-Container verwendet die Konfiguration „web.config appSettings“, um zu steuern, ob die gefälschten Katalogdaten oder die Livedaten des ausgeführten Diensts verwendet werden. Die Anwendung registriert ein HttpModule-Objekt, das den Container erstellt und einen Handler für Voranfragen zum Einfügen der Abhängigkeiten. Sie finden diesen Code in der Datei „Modules/AutoFacHttpModule.cs“. Dieser gleicht dem folgenden Beispiel:

```cs
private static IContainer CreateContainer()
{
  // Configure AutoFac:
  // Register Containers:

  var settings = WebConfigurationManager.AppSettings;
  var useFake = settings["usefake"];
  bool fake = useFake == "true";
  var builder = new ContainerBuilder();

  if (fake)
  {
    builder.RegisterType<CatalogMockService>()
    .As<ICatalogService>();
  }
  else
  {
    builder.RegisterType<CatalogService>()
    .As<ICatalogService>();
    builder.RegisterType<RequestProvider>()
    .As<IRequestProvider>();
  }

  var container = builder.Build();
  return container;
}

private void InjectDependencies()
{
  if (HttpContext.Current.CurrentHandler is Page page)
  {
    // Get the code-behind class that we may have written
    var pageType = page.GetType().BaseType;

    // Determine if there is a constructor to inject, and grab it
    var ctor = (from c in pageType.GetConstructors()
                where c.GetParameters().Length > 0
                select c).FirstOrDefault();

    if (ctor != null)
    {
      // Resolve the parameters for the constructor
      var args = (from parm in ctor.GetParameters()
                  select Container.Resolve(parm.ParameterType))
                  .ToArray();

      // Execute the constructor method with the arguments resolved
      ctor.Invoke(page, args);
    }

    // Use the Autofac method to inject any
    // properties that can be filled by Autofac
    Container.InjectProperties(page);
  }
}
```

Die Anwendungsseiten („Default.aspx.cs“ und „EditPage.aspx.cs“) definieren Konstruktoren, die diese Abhängigkeiten übernehmen. Beachten Sie, dass der Standardkonstruktor weiterhin vorhanden und verfügbar ist. Die Infrastruktur benötigt den folgenden Code.

```cs
protected _Default() { }

public _Default(ICatalogService catalog) => this.catalog = catalog;
```

Alle Katalog-APIs sind asynchrone Methoden. Web Forms unterstützt diese nun für alle Datenkontrollen. Die Catalog.WebForms-Anwendung verwendet die Modellbindung für die Seiten „Liste“ und „Bearbeiten“ und die Steuerelemente auf den Seiten, die die Eigenschaften SelectMethod, UpdateMethod, InsertMethod und DeleteMethod definieren. Diese geben asynchrone Operationen an, die eine Aufgabe zurückgeben. Web Forms-Steuerelemente verstehen, wenn die Methoden, die an ein Steuerelement gebunden sind, asynchron sind. Die einzige Einschränkung beim Verwenden von asynchronen Select-Methoden ist die, dass diese kein Paging unterstützen. Die Pagingsignatur erfordert einen Out-Parameter, asynchrone Methoden können jedoch keine Out-Parameter besitzen. Die gleiche Technik wird für andere Seiten verwendet, die Daten aus dem Katalogdienst benötigen.

Die Standardkonfiguration für die Web Forms-Kataloganwendung verwendet eine Pseudoimplementierung des catalog.api-Diensts. Dieses Mock verwendet einen hartcodierten Datensatz für seine Daten, durch den einige Aufgaben vereinfacht werden, indem die Abhängigkeit vom catalog.api-Dienst aus den Entwicklungsumgebungen entfernt wird.

## <a name="lifting-and-shifting"></a>Lift & Shift

Visual Studio bietet eine umfassende Unterstützung für das Containerisieren einer Anwendung. Klicken Sie mit der rechten Maustaste auf den Projektknoten, und klicken Sie dann auf **Hinzufügen** und **Docker-Unterstützung**. Durch die Docker-Projektvorlage wird ein neues Projekt namens **Docker-Compose** zu der Projektmappe hinzugefügt. Das Projekt enthält die Docker-Objekte, aus denen die erforderlichen Images zusammengesetzt (oder erstellt) werden und führt wie in Abbildung 7-3 dargestellt die benötigten Container aus.

In den einfachsten Lift & Shift-Szenarios ist die Anwendung ein einzelner Dienst, den Sie für die Web Forms-Anwendung verwenden. Die Vorlage ändert auch Ihr Startprojekt, damit dieses auf das **Docker-Compose**-Projekt zeigt. Durch das Drücken von STRG+F5 oder F5 wird nun ein Docker-Image erstellt und der Docker-Container gestartet.

![](./media/image3.png)

**Abbildung 7-3**. Das **Docker-Compose**-Projekt in der Web Forms-Projektmappe

Versichern Sie sich vor dem Ausführen der Projektmappe, dass Sie Docker für das Verwenden von Windows-Containern konfiguriert haben. Klicken Sie dazu unter Windows mit der rechten Maustaste auf das Docker-Taskleistensymbol, und wählen Sie wie in Abbildung 7-4 gezeigt **Switch to Windows Containers** (Wechseln zu Windows-Containern) aus.

![](./media/image4.png)

**Abbildung 7-4**. Wechseln zu Windows-Containern mit dem Docker-Taskleistensymbol unter Windows

Wenn das Menüelement **Switch to Linux containers** (Wechseln zu Linux-Containern) anzeigt, führen Sie Docker bereits mit Windows-Containern aus.

Das Ausführen der Projektmappe startet den Docker-Host neu. Während des Buildprozesses werden die Anwendung und das Docker-Image für das Web Forms-Projekt erstellt. Beim ersten Mal beansprucht dies sehr viel Zeit. Das liegt daran, dass der Buildprozess das Windows Server-Basisimage und das zusätzliche Image für ASP.NET abruft. Nachfolgende Build- und Ausführungszyklen sind wesentlich schneller.

Sehen Sie sich die von der Docker-Projektvorlage hinzugefügten Dateien genauer an. Diese hat mehrere Dateien für Sie erstellt. Visual Studio verwendet diese Dateien, um ein Docker-Image zu erstellen und einen Container zu starten. Sie können die Dateien der CLI verwenden, um Docker-Befehle manuell auszuführen.

Das folgende Dockerfile-Beispiel zeigt die Grundeinstellungen für das Erstellen eines Docker-Images, das auf dem Windows ASP.NET-Image basiert, das eine ASP.NET-Website ausführt.

```
FROM microsoft/aspnet

ARG source

WORKDIR /inetpub/wwwroot

COPY ${source:-obj/Docker/publish} .
```

Diese Dockerfile ähnelt denen, die zum Ausführen einer ASP.NET Core-Anwendung in Linux-Containern erstellt wurden. Es gibt jedoch ein paar wichtige Unterschiede. Der wichtigste Unterschied ist der, dass das Basisimage „microsoft/aspnet“ ist, bei dem es sich um das aktuelle Windows Server-Image handelt, das .NET Framework enthält. Ein weiterer Unterschied ist der, dass die Verzeichnisse, die aus Ihrem Quellverzeichnis kopiert werden, sich unterscheiden.

Die anderen Dateien im **Docker-Compose**-Projekt sind die Docker-Objekte, die zum Erstellen und Konfigurieren des Containers erforderlich sind. Visual Studio legt die verschiedenen YML-Dateien von Docker-Compose in einem Knoten ab, um hervorzuheben, wie sie verwendet werden. Die Docker-Compose-Datei enthält die Anweisungen, die für alle Konfigurationen verfügbar sind. Die Datei „docker-compose.override.yml“ enthält Umgebungsvariablen und die zugehörigen Außerkraftsetzungen für eine Entwicklerkonfiguration. Die Varianten mit „.vs.debug“ und „.vs.release“ stellen Umgebungseinstellungen bereit, die es Visual Studio ermöglichen, an den ausgeführten Container anzufügen und ihn zu verwalten.

Beim Hinzufügen der Docker-Unterstützung zu Ihrer Projektmappe wird Visual Studio integriert. Sie können jedoch auch aus der Befehlszeile erstellen und ausführen, indem Sie den im vorherigen Abschnitt beschriebenen Befehl „docker-compose up“ verwenden.

## <a name="getting-data-from-the-existing-catalog-net-core-microservice"></a>Abrufen von Daten aus dem bestehenden Katalog des .NET Core-Microservices

Sie können die Web Forms-Anwendung konfigurieren, um mithilfe des eShopOnContainers-Katalog-Microservices Daten abzurufen anstatt gefälschte Daten zu verwenden. Bearbeiten Sie dazu die web.config-Datei, und legen Sie den Wert des useFake-Schlüssels auf FALSE fest. Der DI-Container verwendet die Klasse, die auf den Livekatalog von Microservice zugreift, statt der Klasse, die die hartcodierten Daten zurückgibt. Es sind keine anderen Änderungen am Code erforderlich.

Für den Zugriff auf den Livekatalogdienst müssen Sie das **Docker-Compose**-Projekt aktualisieren, um das Katalogdienstimage zu erstellen und den Katalogdienstcontainer zu starten. Docker CE für Windows unterstützt Linux- und Windows-Container, jedoch nicht gleichzeitig. Zum Ausführen des Katalog-Microservices müssen Sie ein Image erstellen, das auf dem Katalog-Microservice zusätzlich zum Windows-basierten Container ausgeführt wird. Diese Vorgehensweise erfordert eine andere Dockerfile für das Microservice-Projekt als in den vorherigen Abschnitten. Die Windows-Datei „Dockerfile“ enthält die Konfigurationseinstellungen für das Erstellen eines Containerimages für die Katalog-API, sodass diese beispielsweise für das Verwenden eines Windows Nano-Docker-Images auf einem Windows-Container ausgeführt werden kann.

Der Katalog-Microservice basiert auf der SQL Server-Datenbank. Deshalb müssen Sie zusätzlich ein Windows-basiertes SQL Server-Docker-Image verwenden.

Nach diesen Änderungen bietet das Docker-Compose-Projekt mehr als das Starten der Anwendung. Das Projekt startet nun den SQL-Server, der das Windows-basierte SQL Server-Image verwendet. Es startet den Katalog-Microservice in einem Windows-Container. Es startet ebenfalls den Web Forms-Container für den Katalog-Editor in einem Windows-Container. Wenn eines der Images noch erstellt werden muss, wird dies zuerst durchgeführt.

## <a name="development-and-production-environments"></a>Entwicklungs- und Produktionsumgebungen

Es gibt einige Unterschiede zwischen der Entwicklungskonfiguration und einer Produktionskonfiguration. In der Entwicklungsumgebung führen Sie die Web Forms-Anwendung, den Katalog-Microservice und SQL Server in Windows-Containern als Teil desselben Docker-Hosts aus. In vorherigen Abschnitten wurden SQL Server-Images erwähnt, die im selben Docker-Host wie die anderen auf .NET Core basierten Dienste in einem Linux-basierten Docker-Host bereitgestellt wurden. Der Vorteil des Ausführens von mehreren Microservices im selben Docker-Host (oder -Cluster) ist der, dass es weniger Netzwerkkommunikation gibt und die Kommunikation zwischen Containern eine geringere Latenz aufweist.

In der Entwicklungsumgebung müssen Sie alle Container auf dem gleichen Betriebssystem ausführen. Docker CE für Windows unterstützt nicht das gleichzeitige Ausführen von Windows- und Linux-basierten Containern. In der Produktion können Sie entscheiden, ob Sie den Katalog-Microservice in einem Windows-Container in einem einzigen Docker-Host (oder -Cluster) ausführen möchten, oder ob Sie möchten, dass die Web Forms-Anwendung mit einer Instanz des Katalog-Microservices kommuniziert, der in einem Linux-Container in einem anderen Docker-Host ausgeführt wird. Das hängt davon ab, wie Sie die Netzwerklatenz optimieren möchten. In den meisten Fällen sollten Ihre Anwendungen von der Ausführung im selben Docker-Host (oder -Schwarm) abhängig sein, um die Bereitstellung zu erleichtern und die Kommunikationslatenz zu verringern. In diesen Konfigurationen findet die einzige kostspielige Kommunikation zwischen den Microservice-Instanzen und den Hochverfügbarkeitsdiensten des beständigen Datenspeichers statt.

>[!div class="step-by-step"]
[Zurück](../net-core-single-containers-linux-windows-server-hosts/index.md)
[Weiter](../multi-container-microservice-net-applications/index.md)
