---
title: 'global.json: Übersicht'
description: In diesem Artikel erfahren Sie, wie Sie mit der global.json-Datei die .NET Core SDK-Version beim Ausführen eines .NET Core-CLI-Befehls festgelegen.
ms.topic: how-to
ms.date: 05/01/2020
ms.custom: updateeachrelease
ms.openlocfilehash: 714e32ec841cee214f801de65bccf0041af66b0b
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93281544"
---
# <a name="globaljson-overview"></a>global.json: Übersicht

**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen

Mit der *global.json* -Datei können Sie definieren, welche .NET Core SDK-Version verwendet wird, wenn Sie .NET Core-CLI-Befehle ausführen. Die Auswahl der .NET Core SDK ist unabhängig von der Angabe der Laufzeit Ihrer Projektziele. Die .NET Core SDK-Version gibt an, welche Version der .NET Core-CLI verwendet wird.

Wenn Sie die neueste Version der SDK-Tools verwenden möchten, wird in der Regel keine *global.json* -Datei benötigt. In einigen Szenarios für Fortgeschrittene sollten Sie die Version der SDK-Tools überwachen. Wie Sie dabei vorgehen müssen, wird in diesem Artikel erläutert.

Weitere Informationen zum Angeben der Laufzeit finden Sie unter [Zielframeworks](../../standard/frameworks.md).

.NET Core SDK sucht im aktuellen Arbeitsverzeichnis (das nicht dem Projektverzeichnis entsprechen muss) oder in einem übergeordneten Verzeichnis nach einer *global.json* -Datei.

## <a name="globaljson-schema"></a>global.json-Schema

### <a name="sdk"></a>SDK

Typ: `object`

Gibt Informationen zum auszuwählenden .NET Core SDK an.

#### <a name="version"></a>Version

- Typ: `string`

- Verfügbar seit dem .NET Core 1.0 SDK

Die Version des zu verwendenden .NET Core SDK.

Dieses Feld:

- unterstützt keine Platzhalter, weshalb die vollständige Versionsnummer angegeben werden muss
- Keine Versionsbereiche unterstützt

#### <a name="allowprerelease"></a>allowPrerelease

- Typ: `boolean`

- Verfügbar seit dem .NET Core 3.0 SDK.

Gibt an, ob der SDK-Resolver bei der Auswahl der zu verwendenden SDK-Version Vorabversionen berücksichtigen soll.

Wenn Sie diesen Wert nicht explizit festlegen, ist der Standardwert davon abhängig, ob Sie Visual Studio für die Ausführung verwenden:

- Wenn Sie **nicht** Visual Studio verwenden, lautet der Standardwert `true`.
- Wenn Sie Visual Studio verwenden, wird der angeforderte Status der Vorabversion verwendet. Das bedeutet, dass bei der Verwendung einer Vorabversion von Visual Studio oder beim Festlegen der Option **Vorschauversionen des .NET Core SDK verwenden** (unter **Extras** > **Optionen** > **Umgebung** > **Preview Features** (Vorschaufeatures)) der Standardwert `true` verwendet wird. Ansonsten wird der Wert `false` verwendet.

#### <a name="rollforward"></a>rollForward

- Typ: `string`

- Verfügbar seit dem .NET Core 3.0 SDK.

Die Rollforwardrichtlinie, die beim Auswählen einer SDK-Version verwendet werden soll, entweder als Fallback, wenn eine bestimmte SDK-Version fehlt, oder als Anweisung, damit eine höhere Version verwendet wird. Eine [Version](#version) muss mit einem `rollForward`-Wert angegeben werden, wenn sie nicht auf `latestMajor` festgelegt ist.
Das standardmäßige Verhalten beim Rollforward wird von den [Abgleichsregeln](#matching-rules) bestimmt.

Lesen Sie sich die folgenden Definitionen für SDK-Versionen im Format `x.y.znn` durch, um sich ein Bild von den verfügbaren Richtlinien und deren Verhalten zu machen.

- `x` ist die Hauptversion.
- `y` ist die Nebenversion.
- `z` ist die Featuregruppe.
- `nn` ist die Patchversion.

In der folgenden Tabelle werden die verschiedenen möglichen Werte für den Schlüssel `rollForward` angezeigt:

| Wert         | Verhalten |
| ------------- | ---------- |
| `patch`       | Verwendet die angegebene Version. <br> Wenn dieser Wert nicht gefunden wird, wird ein Rollforward auf die neuste Patchebene ausgeführt. <br> Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst. <br><br> Dieser Wert steht für das Legacyverhalten aus früheren Versionen des SDK. |
| `feature`     | Verwendet die aktuelle Patchebene für die angegebene Haupt- und Nebenversion sowie die angegebene Featuregruppe. <br> Wenn dieser Wert nicht gefunden wird, wird eine Rollforward auf die nächsthöhere Featuregruppe innerhalb derselben Haupt- bzw. Nebenversion ausgeführt, und es wird die neuste Patchebene für diese Featuregruppe verwendet. <br> Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst. |
| `minor`       | Verwendet die aktuelle Patchebene für die angegebene Haupt- und Nebenversion sowie die angegebene Featuregruppe. <br> Wenn dieser Wert nicht gefunden wird, wird ein Rollforward auf die nächsthöhere Featuregruppe innerhalb derselben Haupt- bzw. Nebenversion ausgeführt, und es wird die neuste Patchebene für diese Featuregruppe verwendet. <br> Wenn dieser Wert nicht gefunden wird, wird eine Rollforward auf die nächsthöhere Nebenversion und die nächsthöhere Featuregruppe innerhalb derselben Hauptversion ausgeführt, und es wird die neuste Patchebene für diese Featuregruppe verwendet. <br> Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst. |
| `major`       | Verwendet die aktuelle Patchebene für die angegebene Haupt- und Nebenversion sowie die angegebene Featuregruppe. <br> Wenn dieser Wert nicht gefunden wird, wird ein Rollforward auf die nächsthöhere Featuregruppe innerhalb derselben Haupt- bzw. Nebenversion ausgeführt, und es wird die neuste Patchebene für diese Featuregruppe verwendet. <br> Wenn dieser Wert nicht gefunden wird, wird eine Rollforward auf die nächsthöhere Nebenversion und die nächsthöhere Featuregruppe innerhalb derselben Hauptversion ausgeführt, und es wird die neuste Patchebene für diese Featuregruppe verwendet. <br> Wenn dieser Wert nicht gefunden wird, wird eine Rollforward auf die nächsthöhere Haupt-, Nebenversion und Featuregruppe ausgeführt, und es wird die neuste Patchebene für diese Featuregruppe verwendet. <br> Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst. |
| `latestPatch` | Verwendet die neuste installierte Patchebene, die mit der angeforderten Haupt-, Nebenversion und Featuregruppe mit einer Patchebene übereinstimmt und größer als der angegebene Wert ist oder diesem entspricht. <br> Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst. |
| `latestFeature` | Verwendet die höchste installierte Featuregruppe und Patchebene, die mit der angeforderten Haupt- und Nebenversion mit einer Featuregruppe und einer Patchebene übereinstimmt, die größer als der angegebene Wert ist oder diesem entspricht. <br> Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst. |
| `latestMinor` | Verwendet die höchste installierte Nebenversion, Featuregruppe und Patchebene, die mit der angeforderten Hauptversion mit einer Nebenversion, einer Featuregruppe und einer Patchebene übereinstimmt, die größer als der angegebene Wert ist oder diesem entspricht. <br> Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst. |
| `latestMajor` | Verwendet das höchste installierte .NET Core SDK mit einer Version, die größer als der angegebene Wert ist oder diesem entspricht. <br> Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst. |
| `disable`     | Es wird kein Rollforward ausgeführt. Es ist eine exakte Übereinstimmung erforderlich. |

### <a name="msbuild-sdks"></a>msbuild-sdks

Typ: `object`

Ermöglicht Ihnen die Kontrolle der SDK-Version des Projekts an einem einzigen Ort anstatt in jedem Projekt einzeln. Weitere Informationen finden Sie unter [Lösen von Projekt SDKs](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved).

## <a name="examples"></a>Beispiele

Das folgende Beispiel zeigt, wie Sie verhindern können, dass Vorabversionen verwendet werden:

```json
{
  "sdk": {
    "allowPrerelease": false
  }
}
```

Im folgenden Beispiel wird gezeigt, wie Sie festlegen können, dass die höchste installierte Version verwendet wird, die höher als die angegebene Version ist oder dieser entspricht. Der gezeigte JSON-Code lässt keine niedrigere SDK-Version als 2.2.200 zu und lässt 2.2.200 oder jede höhere Version zu, einschließlich 3.0.xxx und 3.1.xxx.

```json
{
  "sdk": {
    "version": "2.2.200",
    "rollForward": "latestMajor"
  }
}
```

Das folgende Beispiel zeigt, wie Sie festlegen können, welche genaue Version verwendet werden soll:

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "disable"
  }
}
```

Das folgende Beispiel zeigt, wie das neueste Featureband und die neueste Patchversion verwendet werden, die von einer bestimmten Haupt- und Nebenversion installiert wurden. Der gezeigte JSON-Code lässt keine niedrigere SDK-Version als 3.1.102 zu und lässt 3.1.102 oder jede höhere 3.1.xxx-Version zu, z. B. 3.1.103 oder 3.1.200.

```json
{
  "sdk": {
    "version": "3.1.102",
    "rollForward": "latestFeature"
  }
}
```

Im folgenden Beispiel wird gezeigt, wie Sie festlegen können, dass die höchste installierte Patchversion einer bestimmten Version verwendet wird. Der gezeigte JSON-Code lässt keine niedrigere SDK-Version als 3.1.102 zu und lässt 3.1.102 oder jede höhere 3.1.1xx-Version zu, z. B. 3.1.103 oder 3.1.199.

```json
{
  "sdk": {
    "version": "3.1.102",
    "rollForward": "latestPatch"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a>global.json und die .NET Core-CLI

Sie sollten sich darüber informieren, welche SDK-Versionen auf Ihrem Computer installiert sind, um auch in Ihrer *global.json* -Datei eine Version festzulegen. Weitere Informationen dazu finden Sie unter [Überprüfen, ob .NET Core bereits installiert ist](../install/how-to-detect-installed-versions.md#check-sdk-versions).

Weitere .NET Core SDK-Versionen, die Sie auf Ihrem Computer installieren können, finden Sie unter [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core).

Sie können im aktuellen Verzeichnis eine neue *global.json* -Datei erstellen, indem Sie den Befehl [dotnet new](dotnet-new.md) ausführen, wie im folgenden Beispiel:

```dotnetcli
dotnet new globaljson --sdk-version 3.0.100
```

## <a name="matching-rules"></a>Abgleichsregeln

> [!NOTE]
> Die Abgleichsregeln werden vom Einstiegspunkt `dotnet.exe` geregelt, der für alle installierten .NET Core-Runtimes gleich ist. Die Abgleichsregeln für die neuste installierte Version der .NET Core-Runtime werden verwendet, wenn mehrere Runtimes parallel installiert sind oder Sie die Datei *global.json* verwenden.

## <a name="net-core-3x"></a>[.NET Core 3.x](#tab/netcore3x)

Ab .NET Core 3.0 gelten die folgenden Regeln, wenn ermittelt wird, welche SDK-Version verwendet werden soll:

- Wenn keine *global.json* -Datei gefunden wird oder in der *global.json* -Datei weder eine SDK-Version noch ein `allowPrerelease`-Wert angegeben wird, wird die höchste installierte SDK-Version verwendet (entspricht dem Festlegen von `rollForward` auf `latestMajor`). Ob Vorabversionen von SDKs berücksichtigt werden, ist davon abhängig, wie `dotnet` aufgerufen wird.
  - Wenn Sie **nicht** Visual Studio verwenden, werden Vorabversionen berücksichtigt.
  - Wenn Sie Visual Studio verwenden, wird der angeforderte Status der Vorabversion verwendet. Das bedeutet, dass bei der Verwendung einer Vorabversion von Visual Studio oder beim Festlegen der Option **Vorschauversionen des .NET Core SDK verwenden** (unter **Extras** > **Optionen** > **Umgebung** > **Preview Features** (Vorschaufeatures)) Vorabversionen berücksichtigt werden. Andernfalls werden nur Releaseversionen berücksichtigt.
- Wenn eine *global.json* -Datei gefunden wird, in der keine SDK-Version, aber dafür ein `allowPrerelease`-Wert angegeben ist, wird die höchste installierte SDK-Version verwendet (entspricht dem Festlegen von `rollForward` auf `latestMajor`). Ob es sich bei der neusten SDK-Version um ein Release handeln muss oder ob Vorabversionen akzeptiert werden, hängt vom Wert `allowPrerelease` ab. `true` gibt an, dass Vorabversionen berücksichtigt werden, während bei `false` nur Releases berücksichtigt werden.
- Wenn eine *global.json* -Datei gefunden wird und in dieser eine SDK-Version angegeben ist, geschieht Folgendes:

  - Wenn kein `rollForward`-Wert festgelegt ist, wird `latestPatch` als `rollForward`-Standardrichtlinie verwendet. Überprüfen Sie andernfalls die einzelnen Werte und deren Verhalten im Abschnitt [rollForward](#rollforward).
  - Im Abschnitt [allowPrerelease](#allowprerelease) wird beschrieben, ob Vorabversionen berücksichtigt werden, und es wird das Standardverhalten festgelegt, wenn `allowPrerelease` nicht festgelegt ist.

## <a name="net-core-2x"></a>[.NET Core 2.x](#tab/netcore2x)

Im .NET Core 2.x SDK gelten die folgenden Regeln, wenn ermittelt wird, welche Version des SDK verwendet werden soll:

- Wenn keine *global.json* -Datei gefunden wird oder *global.json* keine SDK-Version angibt, wird die neueste installierte SDK-Version verwendet. Die neuste SDK-Version kann ein Release oder eine Vorabversion sein – es gilt die höchste Versionsnummer.
- Wenn *global.json* eine SDK-Version angibt:
  - Wenn die angegebene SDK-Version auf dem Computer gefunden wird, wird genaue diese Version verwendet.
  - Wenn die angegebene SDK-Version auf dem Computer nicht gefunden wird, wird die neueste installierte SDK- **Patchversion** der Version verwendet. Die neuste installierte SDK- **Patchversion** kann ein Release oder eine Vorabversion sein – es gilt die höchste Versionsnummer. In .NET Core 2.1 und höher werden die **Patchversionen** , die niedriger als die angegebene **Patchversion** sind, bei der SDK-Auswahl ignoriert.
  - Wenn die angegebene SDK-Version und eine entsprechende SDK- **Patchversion** nicht gefunden werden, wird ein Fehler ausgelöst.

Die SDK-Version hat folgende Bestandteile:

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

Die **Funktionsfreigabe** von .NET Core SDK wird für SDK-Versionen ab 2.1.100 von der ersten Ziffer (`x`) im letzten Teil der Nummer (`xyz`) dargestellt. Generell hat .NET Core SDK einen schnelleren Releasezyklus als .NET Core.

Die **Patchversion** wird für SDK-Versionen ab 2.1.100 von den letzten beiden Ziffern (`yz`) im letzten Teil der Nummer (`xyz`) definiert. Wenn Sie beispielsweise `2.1.300` als SDK-Version angeben, werden für die SDK-Auswahl Versionen bis `2.1.399` berücksichtigt, allerdings wird `2.1.400` nicht als Patchversion von `2.1.300` betrachtet.

.NET Core SDK-Versionen `2.1.100` bis `2.1.201` wurden beim Übergang zwischen Versionsnummerschemen freigegeben und halten die `xyz`-Notation nicht ordnungsgemäß ein. Falls Sie diese Versionen in der *global.json* -Datei angeben, wird dringend empfohlen sicherzustellen, dass sich die angegebenen Versionen auf den Zielcomputern befinden.

---

## <a name="troubleshoot-build-warnings"></a>Problembehandlung bei Buildwarnungen

* Die folgende Warnung weist darauf hin, dass das Projekt mit einer Vorabversion des .NET Core SDK kompiliert wurde:

  > Sie verwenden eine Vorschauversion von .NET Core SDK. Sie können die SDK-Version über eine global.json-Datei im aktuellen Projekt definieren. Weitere Informationen finden Sie unter <https://go.microsoft.com/fwlink/?linkid=869452>.

  .NET Core SDK-Versionen haben einen Verlauf und weisen eine hohe Qualität auf. Wenn Sie jedoch keine Vorabversion verwenden möchten, prüfen Sie im Abschnitt [allowPrerelease](#allowprerelease) die verschiedenen Strategien, die Sie mit dem .NET Core 3.0 SDK oder einer höheren Version verwenden können. Für Computer, auf denen eine Runtime oder ein SDK für .NET Core 3.0 oder höher installiert ist, benötigen Sie eine *global.json* -Datei und müssen die genaue Version angeben, die verwendet werden soll.

* Die folgende Warnung gibt an, dass Ihr Projekt für EF Core 1.0 oder 1.1 ausgelegt ist. Diese Versionen sind nicht mit dem .NET Core 2.1 SDK und höheren Versionen verfügbar:

  > Das Startprojekt „{startupProject}“ gibt Version „{targetFrameworkVersion}“ von Framework „.NETCoreApp“ als Ziel an. Diese Version der Entity Framework Core .NET-Befehlszeilentools unterstützt nur Version 2.0 oder höher. Weitere Informationen zur Verwendung älterer Toolversionen finden Sie unter <https://go.microsoft.com/fwlink/?linkid=871254>.

  Ab .NET Core 2.1 SDK (Version 2.1.300) ist der Befehl `dotnet ef` im SDK enthalten. Installieren Sie das .NET Core 2.0 SDK (Version 2.1.201) oder früher auf Ihrem Computer, und definieren Sie die gewünschte Version des SDKs mithilfe der Datei *global.json* , um Ihr Projekt zu kompilieren. Weitere Informationen zu dem Befehl `dotnet ef` finden Sie unter [EF Core .NET-Befehlszeilentools](/ef/core/miscellaneous/cli/dotnet).

## <a name="see-also"></a>Siehe auch

- [Wie Projekt-SDKs gelöst werden](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
