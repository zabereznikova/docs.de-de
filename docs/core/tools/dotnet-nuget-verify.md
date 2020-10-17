---
title: dotnet nuget verify-Befehl
description: Der dotnet nuget verify-Befehl überprüft ein signiertes Paket.
author: kartheekp-ms
ms.date: 10/08/2020
ms.openlocfilehash: 6cb368e2b6c203f3774b4450c0831c5d6b2dc0e8
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957091"
---
# <a name="dotnet-nuget-verify"></a>dotnet nuget verify

**Dieser Artikel gilt für:** ✔️ .NET 5.0.100-rc.2.x SDK und neuere Versionen

## <a name="name"></a>Name

`dotnet nuget verify`: Hiermit wird ein signiertes NuGet-Paket überprüft.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet nuget verify [<package-path(s)>]
    [--all]
    [--certificate-fingerprint <FINGERPRINT>]
    [-v|--verbosity <LEVEL>]

dotnet nuget verify -h|--help
```

## <a name="description"></a>Beschreibung

Mit dem `dotnet nuget verify`-Befehl wird ein signiertes NuGet-Paket überprüft.

## <a name="arguments"></a>Argumente

- **`package-path(s)`**

  Hiermit wird der Dateipfad der Pakete angegeben, die überprüft werden sollen. Zur Überprüfung mehrere Pakete können mehrere Argumente übergeben werden.

## <a name="options"></a>Tastatur

- **`--all`**

  Hiermit wird angegeben, dass alle Überprüfungen für die Pakete ausgeführt werden sollen, die möglich sind. Standardmäßig finden nur `signatures`-Überprüfungen statt.

> [!NOTE]
> Dieser Befehl unterstützt aktuell nur die `signature`-Überprüfung.

- **`--certificate-fingerprint <FINGERPRINT>`**

  Hiermit wird überprüft, ob das Signaturzertifikat mit einem der angegebenen `SHA256`-Fingerabdrücke übereinstimmt. Diese Option kann mehrfach bereitgestellt werden, um mehrere Fingerabdrücke bereitzustellen.

* **`-v|--verbosity <LEVEL>`**

  Legt den MSBuild-Ausführlichkeitsgrad fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`. Der Standardwert ist `normal`.

* **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

- Überprüfen Sie *foo.nupkg:*

  ```dotnetcli
  dotnet nuget verify foo.nupkg
  ```

- Hiermit werden mehrere NuGet-Pakete überprüft: *foo.nupkg* sowie *alle NUPGK-Dateien im angegebenen Verzeichnis:*

  ```dotnetcli
  dotnet nuget verify foo.nupkg c:\mydir\*.nupkg
  ```

- Hiermit wird überprüft, ob die *foo.nupgk*-Signatur mit dem angegebenen Zertifikatfingerabdruck übereinstimmt:

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039
  ```

- Hiermit wird überprüft, ob die *foo.nupgk*-Signatur mit einem der angegebenen Zertifikatfingerabdrücken übereinstimmt:

  ```dotnetcli
  dotnet nuget verify foo.nupkg --certificate-fingerprint CE40881FF5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E039 --certificate-fingerprint EC10992GG5F0AD3E58965DA20A9F571EF1651A56933748E1BF1C99E537C4E027
  ```
