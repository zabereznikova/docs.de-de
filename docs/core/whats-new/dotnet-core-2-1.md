---
title: Neuigkeiten in .NET Core 2.1
description: Informationen zu den neuen Features in .NET Core 2.1.
dev_langs:
- csharp
- vb
ms.date: 10/10/2018
ms.openlocfilehash: 78d9a6490c0479d9c21e01d0bcba41294d674a5c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644386"
---
# <a name="whats-new-in-net-core-21"></a>Neuigkeiten in .NET Core 2.1

.NET Core 2.1 enthält Verbesserungen und neue Features in folgenden Bereichen:

- [Tools](#tooling)
- [Rollforward](#roll-forward)
- [Bereitstellung](#deployment)
- [Windows Compatibility Pack](#windows-compatibility-pack)
- [JIT-Kompilierungsverbesserungen](#jit-compiler-improvements)
- [API-Änderungen](#api-changes)

## <a name="tooling"></a>Tools

Das .NET Core 2.1 SDK (Version 2.1.300), die in .NET Core 2.1 enthaltenen Tools, enthält die folgenden Änderungen und Verbesserungen:

### <a name="build-performance-improvements"></a>Buildleistungsverbesserungen

Ein wichtiger Schwerpunkt von .NET Core 2.1 ist die Verbesserung der Buildzeitleistung, insbesondere bei inkrementellen Builds. Diese Leistungsverbesserungen gelten sowohl für beide Befehlszeilenbuilds mit `dotnet build` als auch Builds in Visual Studio. Einige individuelle Verbesserungsbereiche sind:

- Bei der Auflösung von Paketressourcen werden statt aller Ressourcen nur die von einem Build verwendeten Ressourcen aufgelöst.

- Zwischenspeichern von Assemblyverweisen.

- Verwendung von SDK-Buildservern mit langer Ausführungszeit, wobei es sich um Prozesse handelt, die sich über einzelne `dotnet build`-Aufrufe erstrecken. Sie machen die Notwendigkeit der JIT-Kompilierung großer Codeblöcke bei jeder Ausführung von `dotnet build` überflüssig. Buildserverprozesse können automatisch mithilfe des folgenden Befehls beendet werden:

   ```dotnetcli
   dotnet buildserver shutdown
   ```

### <a name="new-cli-commands"></a>Neue CLI-Befehle

Eine Reihe von Tools, die nur auf Projektbasis unter Verwendung von `DotnetCliToolReference` verfügbar waren, steht jetzt als Teil des .NET Core SDK zur Verfügung. Zu diesen Tools gehören:

- `dotnet watch` bietet eine Dateisystemüberwachung, die vor der Ausführung eines designierten Satzes von Befehlen auf die Änderung einer Datei wartet. Der folgende Befehl erstellt beispielsweise automatisch das aktuelle Projekt neu und generiert eine ausführliche Ausgabe, sobald sich eine Datei darin ändert:

   ```dotnetcli
   dotnet watch -- --verbose build
   ```

   Beachten Sie, dass die `--`-Option der `--verbose`-Option vorausgeht. Sie begrenzt die Optionen, die dem `dotnet watch`-Befehl direkt von den Argumenten übergeben werden, die dem untergeordneten `dotnet`-Prozess übergeben werden. Ohne sie gilt die `--verbose`-Option für den `dotnet watch`-Befehl, nicht den `dotnet build`-Befehl.
  
   Weitere Informationen finden Sie unter [Entwickeln von ASP.NET Core-Apps mit dotnet watch](/aspnet/core/tutorials/dotnet-watch).

- `dotnet dev-certs` generiert und verwaltet Zertifikate, die während der Entwicklung in ASP.NET Core-Anwendungen verwendet werden.

- `dotnet user-secrets` verwaltet die Geheimnisse in einem Benutzergeheimnisspeicher in ASP.NET Core-Anwendungen.

- `dotnet sql-cache` erstellt eine Tabelle und Indizes für Distributed Caching in einer Microsoft SQL Server-Datenbank.

- `dotnet ef` ist ein Tool zum Verwalten von Datenbanken, <xref:Microsoft.EntityFrameworkCore.DbContext>-Objekten und Migrationen in Entity Framework Core-Anwendungen. Weitere Informationen finden Sie unter [EF Core .NET-Befehlszeilentools](/ef/core/miscellaneous/cli/dotnet).

### <a name="global-tools"></a>Globale Tools

.NET Core 2.1 unterstützt *globale Tools* – d.h. benutzerdefinierte Tools, die global über die Befehlszeile verfügbar sind. Das Erweiterbarkeitsmodell in früheren Versionen von benutzerdefinierten .NET Core-Tools ist auf Projektbasis nur mithilfe von `DotnetCliToolReference` verfügbar.

Verwenden Sie den [dotnet tool install](../tools/dotnet-tool-install.md)-Befehl, um ein globales Tool zu installieren. Zum Beispiel:

```dotnetcli
dotnet tool install -g dotnetsay
```

Nach Abschluss der Installation kann das Tool durch Angeben seines Namens in der Befehlszeile ausgeführt werden. Weitere Informationen finden Sie unter [Übersicht über globale .NET Core-Tools](../tools/global-tools.md).

### <a name="tool-management-with-the-dotnet-tool-command"></a>Toolverwaltung mit dem `dotnet tool`-Befehl

In .NET Core SDK 2.1 verwenden alle Toolsvorgänge den `dotnet tool`-Befehl. Die folgenden Optionen sind verfügbar:

- [`dotnet tool install`](../tools/dotnet-tool-install.md) zum Installieren eines Tools.

- [`dotnet tool update`](../tools/dotnet-tool-update.md) zum Deinstallieren und Neuinstallieren eines Tools, wodurch es eigentlich aktualisiert wird.

- [`dotnet tool list`](../tools/dotnet-tool-list.md) zum Auflisten derzeit installierter Tools.

- [`dotnet tool uninstall`](../tools/dotnet-tool-uninstall.md) zum Deinstallieren derzeit installierter Tools.

## <a name="roll-forward"></a>Rollforward

Ab .NET Core 2.0 wird für alle .NET Core-Anwendungen automatisch ein Rollforward auf die neueste *Nebenversion* auf einem System installiert.

Wenn die Version von .NET Core, mit der eine Anwendung erstellt wurde, nicht zur Runtime vorhanden ist, wird die Anwendung ab .NET Core 2.0 automatisch für die neueste installierte *Nebenversion* von .NET Core ausgeführt. Das heißt, wenn eine Anwendung mit .NET Core 2.0 erstellt wurde, und .NET Core 2.0 auf dem Hostsystem nicht vorhanden ist, jedoch .NET Core 2.1, wird die Anwendung mit .NET Core 2.1 ausgeführt.

> [!IMPORTANT]
> Dieses Rollforwardverhalten gilt nicht für Vorschauversionen. Es wird standardmäßig auch nicht auf Hauptreleases angewendet. Dies können Sie mit den folgenden Einstellungen jedoch ändern.

Sie können dieses Verhalten anpassen, indem Sie die Einstellung für den Rollforward auf das freigegebene Framework ohne Candidate. Folgende Einstellungen sind verfügbar:

- `0`: Das Rollforwardverhalten für Nebenversionen deaktivieren. Mit dieser Einstellung wird für Anwendungen für .NET Core 2.0.0 ein Rollforward auf .NET Core 2.0.1 ausgeführt, aber nicht für .NET Core 2.2.0 oder .NET Core 3.0.0.
- `1`: Das Rollforwardverhalten für Nebenversionen aktivieren. Dies ist die Standardeinstellung. Mit dieser Einstellung wird für Anwendungen für .NET Core 2.0.0 ein Rollforward auf .NET Core 2.0.1 oder .NET Core 2.2.0 abhängig davon ausgeführt, was installiert wird. Es wird jedoch kein Rollforward auf .NET Core 3.0.0 ausgeführt.
- `2`: Das Rollforwardverhalten für Neben- und Hauptversionen aktivieren. Wenn diese Einstellung festgelegt wird, werden auch verschiedene Hauptversionen für das Rollforwardverhalten beachtet, d. h., für Anwendungen für .NET Core 2.0.0 wird ein Rollforward auf .NET Core 3.0.0 ausgeführt.

Sie können diese Einstellung auf drei verschiedene Arten ändern:

- Legen Sie den gewünschten Wert für die Umgebungsvariable `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` fest.

- Fügen Sie die folgende Zeile mit dem gewünschten Wert in die Datei *.runtimeconfig.json* ein:

   ```json
   "rollForwardOnNoCandidateFx" : 0
   ```

- Fügen Sie bei Verwendung der [.NET Core-CLI](../tools/index.md) die folgende Option mit dem gewünschten Wert zu einem .NET Core-Befehl wie `run` hinzu:

   ```dotnetcli
   dotnet run --rollForwardOnNoCandidateFx=0
   ```

Rollforwards für die Patchversionen sind unabhängig von dieser Einstellung und erfolgen erst, nachdem Rollforwards für Neben- und Hauptversionen ausgeführt wurden.

## <a name="deployment"></a>Bereitstellung

### <a name="self-contained-application-servicing"></a>Wartung einer eigenständigen Anwendung

`dotnet publish` veröffentlicht jetzt eigenständige Anwendungen mit einer gewarteten Runtimeversion. Wenn Sie eine eigenständige Anwendung mit dem .NET Core 2.1 SDK (Version 2.1.300) veröffentlichen, enthält Ihre Anwendung die neueste gewartete Runtimeversion, die diesem SDK bekannt ist. Wenn Sie auf das neueste SDK aktualisieren, veröffentlichen Sie mit der neuesten .NET Core-Runtimeversion. Dies gilt für Runtimes ab .NET Core 1.0.

Eigenständige Veröffentlichung basiert auf Runtimeversionen auf „NuGet.org“. Die gewartete Runtime muss nicht auf Ihrem Computer vorhanden sein.

Bei Verwendung von .NET Core 2.0 SDK werden eigenständige Anwendungen mit der .NET Core 2.0.0-Runtime veröffentlicht, solange keine andere Version über die `RuntimeFrameworkVersion`-Eigenschaft angegeben wird. Mit diesem neuen Verhalten müssen Sie diese Eigenschaft nicht mehr festlegen, um eine höhere Runtimeversion für eine eigenständige Anwendung auszuwählen. Der einfachste Ansatz, auf eine höhere Version zu aktualisieren, besteht darin, immer mit .NET Core 2.1 SDK (Version 2.1.300) zu veröffentlichen.

Weitere Informationen finden Sie unter [Rollforward der eigenständigen Runtimebereitstellung](../deploying/runtime-patch-selection.md).
## <a name="windows-compatibility-pack"></a>Windows Compatibility Pack

Wenn Sie vorhandenen Code aus .NET Framework zu .NET Core portieren, können Sie das [Windows Compatibility Pack](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) verwenden. Es bietet Zugriff auf 20.000 APIs mehr, als in .NET Core verfügbar sind. Zu diesen APIs zählen Typen in <xref:System.Drawing?displayProperty=nameWithType>-Namespace, <xref:System.Diagnostics.EventLog>-Klasse, WMI, Leistungsindikatoren, Windows-Diensten sowie die Windows-Registrierungstypen und Member.

## <a name="jit-compiler-improvements"></a>Verbesserungen am JIT-Compiler

.NET Core umfasst eine neue JIT-Compiler-Technologie namens *mehrstufige Kompilierung* (auch bekannt als *adaptive Optimierung*), die die Leistung erheblich verbessern kann. Mehrstufige Kompilierung ist eine optionale Einstellung.

Eine der wichtigen Aufgaben, die vom JIT-Compiler ausgeführt werden, ist die Optimierung der Ausführung des Codes. Für wenig genutzte Codepfade muss der Compiler jedoch möglicherweise mehr Zeit zur Optimierung des Codes aufbringen, als die Runtime zur Ausführung nicht optimierten Codes benötigt. Die mehrstufige Kompilierung unterteilt die JIT-Kompilierung in zwei Phasen:

- Eine **erste Stufe**, die so schnell wie möglich Code generiert.

- Eine **zweite Stufe**, die optimiertem Code für Methoden generiert, die häufig ausgeführt werden. Die zweite Stufe der Kompilierung wird parallel zum Verbessern der Leistung ausgeführt.

Zum Aktivieren der mehrstufigen Kompilierung können Sie zwischen zwei Arten wählen.

- Um mehrstufige Kompilierung in allen Projekten einzusetzen, die das .NET Core 2.1 SDK verwenden, legen Sie die folgende Umgebungsvariable fest:

  ```console
  COMPlus_TieredCompilation="1"
  ```

- Um mehrstufige Kompilierung in ausgewählten Projekten einzusetzen, fügen Sie die `<TieredCompilation>`-Eigenschaft dem `<PropertyGroup>`-Abschnitt der MSBuild-Projektdatei hinzu, wie im folgenden Beispiel gezeigt:

   ```xml
   <PropertyGroup>
      <!-- other property definitions -->

      <TieredCompilation>true</TieredCompilation>
   </PropertyGroup>
   ```

## <a name="api-changes"></a>API-Änderungen

### <a name="spant-and-memoryt"></a>`Span<T>` und `Memory<T>`

.NET Core 2.1 enthält einige neue Typen, die das Arbeiten mit Arrays und anderen Arten von Arbeitsspeicher wesentlich effizienter machen. Die neuen Typen umfassen:

- <xref:System.Span%601?displayProperty=nameWithType> und <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>.

- <xref:System.Memory%601?displayProperty=nameWithType> und <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>.

Ohne diese Typen müssen Sie bei der Übergabe solcher Elemente als Teil eines Arrays oder Abschnitt eines Arbeitsspeicherpuffers eine Kopie eines Teils der Daten anfertigen, bevor Sie sie einer Methode übergeben. Diese Typen bieten eine virtuelle Sicht der Daten, die die zusätzliche Speicherzuweisung und Kopiervorgänge überflüssig macht.

Das folgende Beispiel verwendet eine <xref:System.Span%601>- und eine <xref:System.Memory%601>-Instanz, um eine virtuelle Ansicht von 10 Elementen eines Arrays bereitzustellen.

[!code-csharp[Span\<T>](~/samples/snippets/core/whats-new/whats-new-in-21/csharp/program.cs)]

[!code-vb[Memory\<T>](~/samples/snippets/core/whats-new/whats-new-in-21/vb/program.vb)]

### <a name="brotli-compression"></a>Brotli-Komprimierung

Ab .NET Core 2.1 werden Brotli-Komprimierung und -Dekomprimierung unterstützt. Brotli ist ein allgemein einsetzbarer verlustfreier Komprimierungsalgorithmus, der in [RFC 7932](https://www.ietf.org/rfc/rfc7932.txt) definiert ist und von den meisten Webbrowsern und den wichtigsten Webservern unterstützt wird. Sie können die streambasierte <xref:System.IO.Compression.BrotliStream?displayProperty=nameWithType>-Klasse oder die leistungsstarken, bereichsbasierten Klassen <xref:System.IO.Compression.BrotliEncoder?displayProperty=nameWithType> und <xref:System.IO.Compression.BrotliDecoder?displayProperty=nameWithType> verwenden. Im folgenden Beispiel wird die Komprimierung mit der <xref:System.IO.Compression.BrotliStream>-Klasse veranschaulicht:

[!code-csharp[Brotli compression](~/samples/snippets/core/whats-new/whats-new-in-21/csharp/brotli.cs#1)]

[!code-vb[Brotli compression](~/samples/snippets/core/whats-new/whats-new-in-21/vb/brotli.vb#1)]

Das <xref:System.IO.Compression.BrotliStream>-Verhalten entspricht dem von <xref:System.IO.Compression.DeflateStream> und <xref:System.IO.Compression.GZipStream>. Dies vereinfacht das Konvertieren von Code, der diese APIs nach <xref:System.IO.Compression.BrotliStream> aufruft.

### <a name="new-cryptography-apis-and-cryptography-improvements"></a>Neue Kryptografie-APIs und Kryptografieverbesserungen

.NET Core 2.1 enthält zahlreiche Verbesserungen der Kryptografie-APIs:

- <xref:System.Security.Cryptography.Pkcs.SignedCms?displayProperty=nameWithType> ist im Paket System.Security.Cryptography.Pkcs verfügbar. Die Implementierung ist identisch mit jener der <xref:System.Security.Cryptography.Pkcs.SignedCms>-Klasse in .NET Framework.

- Neue Überladungen der <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHash%2A?displayProperty=nameWithType>- und <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString%2A?displayProperty=nameWithType>-Methode akzeptieren einen Hashalgorithmusbezeichner, um Aufrufern zu ermöglichen, Zertifikatfingerabdruck-Werte mit anderen Algorithmen als SHA-1 zu erhalten.

- Neue Kryptografie-APIs auf <xref:System.Span%601>-Basis stehen für Hashvorgänge, HMAC, kryptografische Zufallszahlengenerierung, asymmetrische Signaturgenerierung, asymmetrische Signaturverarbeitung und RSA-Verschlüsselung zur Verfügung.

- Die Leistung von <xref:System.Security.Cryptography.Rfc2898DeriveBytes?displayProperty=nameWithType> wurde mithilfe einer <xref:System.Span%601>-basierten Implementierung um ca. 15% verbessert.

- Die neue <xref:System.Security.Cryptography.CryptographicOperations?displayProperty=nameWithType>-Klasse enthält zwei neue Methoden:

  - <xref:System.Security.Cryptography.CryptographicOperations.FixedTimeEquals%2A> benötigt eine feste Zeitspanne zur Rückgabe von zwei beliebigen Eingaben derselben Länge, sodass sie zur Verwendung bei kryptografischer Überprüfung geeignet ist, um zu vermeiden, das zu Zeitsteuerungs-Seitenkanalinformationen beigetragen wird.

  - <xref:System.Security.Cryptography.CryptographicOperations.ZeroMemory%2A> ist eine Arbeitsspeicherlöschroutine, die nicht optimiert werden kann.

- Die statische <xref:System.Security.Cryptography.RandomNumberGenerator.Fill%2A?displayProperty=nameWithType>-Methode füllt eine <xref:System.Span%601> mit Zufallswerten.

- Die <xref:System.Security.Cryptography.Pkcs.EnvelopedCms?displayProperty=nameWithType>-Methode wird jetzt unter Linux und macOS unterstützt.

- Elliptic-Curve Diffie-Hellman (ECDH) steht jetzt in der <xref:System.Security.Cryptography.ECDiffieHellman?displayProperty=nameWithType>-Klassenfamilie zur Verfügung. Der Oberflächenbereich ist mit dem von .NET Framework identisch.

- Die von <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> zurückgegebene Instanz kann mit OAEP mit einem SHA-2-Hashwert verschlüsseln oder entschlüsseln als auch Signaturen mit RSA-PSS generieren oder überprüfen.

### <a name="sockets-improvements"></a>Socketverbesserungen

.NET Core umfasst einen neuen Typ, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, und einen umgeschriebenen, <xref:System.Net.Http.HttpMessageHandler?displayProperty=nameWithType>, die gemeinsam die Basis der Netzwerk-APIs auf höherer Ebene bilden.  <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> ist z.B. die Grundlage der <xref:System.Net.Http.HttpClient>-Implementierung. In früheren Versionen von .NET Core basierten APIs auf höherer Ebene auf nativen Netzwerkimplementierungen.

Die in .NET Core 2.1 eingeführte Socketimplementierung hat eine Reihe von Vorteilen:

- Eine beträchtliche Leistungssteigerung im Vergleich zur früheren Implementierung.

- Plattformabhängigkeiten wurden eliminiert, was Bereitstellung und Wartung vereinfacht.

- Einheitliches Verhalten auf allen .NET Core-Plattformen.

<xref:System.Net.Http.SocketsHttpHandler> ist die Standardimplementierung in .NET Core 2.1. Allerdings können Sie Ihre Anwendung mit der älteren <xref:System.Net.Http.HttpClientHandler>-Klasse durch Aufrufen der <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode konfigurieren:

```csharp
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", false);
```

```vb
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", False)
```

Statt auf <xref:System.Net.Http.SocketsHttpHandler> basierender Socketimplementierungen können Sie auch eine Umgebungsvariable verwenden. Legen Sie dazu für `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` entweder `false` oder 0 (null) fest.

Unter Windows können Sie auch <xref:System.Net.Http.WinHttpHandler?displayProperty=nameWithType> verwenden, was von einer nativen Implementierung abhängt, oder die <xref:System.Net.Http.SocketsHttpHandler>-Klasse durch Übergabe einer Instanz der Klasse an den <xref:System.Net.Http.HttpClient>-Konstruktor.

Auf Linux und macOS können Sie <xref:System.Net.Http.HttpClient> nur pro Prozess konfigurieren. Unter Linux müssen Sie [libcurl](https://curl.haxx.se/libcurl/) bereitstellen, wenn Sie die alte <xref:System.Net.Http.HttpClient>-Implementierung verwenden möchten. (Wird mit .NET Core 2.0 installiert.)

### <a name="breaking-changes"></a>Breaking Changes

Informationen zu Breaking Changes finden Sie unter [Breaking Changes für die Migration von Version 2.0 zu 2.1](../compatibility/2.0-2.1.md).

## <a name="see-also"></a>Siehe auch

- [Neuerungen in .NET Core 3.1](dotnet-core-3-1.md)
- [Neue Features in EF Core 2.1](/ef/core/what-is-new/ef-core-2.1)
- [Neuerungen in ASP.NET Core 2.1](/aspnet/core/aspnetcore-2.1)
