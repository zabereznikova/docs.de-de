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
# <a name="globaljson-overview"></a><span data-ttu-id="5361d-103">global.json: Übersicht</span><span class="sxs-lookup"><span data-stu-id="5361d-103">global.json overview</span></span>

<span data-ttu-id="5361d-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="5361d-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

<span data-ttu-id="5361d-105">Mit der *global.json* -Datei können Sie definieren, welche .NET Core SDK-Version verwendet wird, wenn Sie .NET Core-CLI-Befehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="5361d-105">The *global.json* file allows you to define which .NET Core SDK version is used when you run .NET Core CLI commands.</span></span> <span data-ttu-id="5361d-106">Die Auswahl der .NET Core SDK ist unabhängig von der Angabe der Laufzeit Ihrer Projektziele.</span><span class="sxs-lookup"><span data-stu-id="5361d-106">Selecting the .NET Core SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="5361d-107">Die .NET Core SDK-Version gibt an, welche Version der .NET Core-CLI verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5361d-107">The .NET Core SDK version indicates which versions of the .NET Core CLI is used.</span></span>

<span data-ttu-id="5361d-108">Wenn Sie die neueste Version der SDK-Tools verwenden möchten, wird in der Regel keine *global.json* -Datei benötigt.</span><span class="sxs-lookup"><span data-stu-id="5361d-108">In general, you want to use the latest version of the SDK tools, so no *global.json* file is needed.</span></span> <span data-ttu-id="5361d-109">In einigen Szenarios für Fortgeschrittene sollten Sie die Version der SDK-Tools überwachen. Wie Sie dabei vorgehen müssen, wird in diesem Artikel erläutert.</span><span class="sxs-lookup"><span data-stu-id="5361d-109">In some advanced scenarios, you might want to control the version of the SDK tools, and this article explains how to do this.</span></span>

<span data-ttu-id="5361d-110">Weitere Informationen zum Angeben der Laufzeit finden Sie unter [Zielframeworks](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="5361d-110">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="5361d-111">.NET Core SDK sucht im aktuellen Arbeitsverzeichnis (das nicht dem Projektverzeichnis entsprechen muss) oder in einem übergeordneten Verzeichnis nach einer *global.json* -Datei.</span><span class="sxs-lookup"><span data-stu-id="5361d-111">.NET Core SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="5361d-112">global.json-Schema</span><span class="sxs-lookup"><span data-stu-id="5361d-112">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="5361d-113">SDK</span><span class="sxs-lookup"><span data-stu-id="5361d-113">sdk</span></span>

<span data-ttu-id="5361d-114">Typ: `object`</span><span class="sxs-lookup"><span data-stu-id="5361d-114">Type: `object`</span></span>

<span data-ttu-id="5361d-115">Gibt Informationen zum auszuwählenden .NET Core SDK an.</span><span class="sxs-lookup"><span data-stu-id="5361d-115">Specifies information about the .NET Core SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="5361d-116">Version</span><span class="sxs-lookup"><span data-stu-id="5361d-116">version</span></span>

- <span data-ttu-id="5361d-117">Typ: `string`</span><span class="sxs-lookup"><span data-stu-id="5361d-117">Type: `string`</span></span>

- <span data-ttu-id="5361d-118">Verfügbar seit dem .NET Core 1.0 SDK</span><span class="sxs-lookup"><span data-stu-id="5361d-118">Available since: .NET Core 1.0 SDK.</span></span>

<span data-ttu-id="5361d-119">Die Version des zu verwendenden .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="5361d-119">The version of the .NET Core SDK to use.</span></span>

<span data-ttu-id="5361d-120">Dieses Feld:</span><span class="sxs-lookup"><span data-stu-id="5361d-120">This field:</span></span>

- <span data-ttu-id="5361d-121">unterstützt keine Platzhalter, weshalb die vollständige Versionsnummer angegeben werden muss</span><span class="sxs-lookup"><span data-stu-id="5361d-121">Doesn't have wildcard support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="5361d-122">Keine Versionsbereiche unterstützt</span><span class="sxs-lookup"><span data-stu-id="5361d-122">Doesn't support version ranges.</span></span>

#### <a name="allowprerelease"></a><span data-ttu-id="5361d-123">allowPrerelease</span><span class="sxs-lookup"><span data-stu-id="5361d-123">allowPrerelease</span></span>

- <span data-ttu-id="5361d-124">Typ: `boolean`</span><span class="sxs-lookup"><span data-stu-id="5361d-124">Type: `boolean`</span></span>

- <span data-ttu-id="5361d-125">Verfügbar seit dem .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="5361d-125">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="5361d-126">Gibt an, ob der SDK-Resolver bei der Auswahl der zu verwendenden SDK-Version Vorabversionen berücksichtigen soll.</span><span class="sxs-lookup"><span data-stu-id="5361d-126">Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>

<span data-ttu-id="5361d-127">Wenn Sie diesen Wert nicht explizit festlegen, ist der Standardwert davon abhängig, ob Sie Visual Studio für die Ausführung verwenden:</span><span class="sxs-lookup"><span data-stu-id="5361d-127">If you don't set this value explicitly, the default value depends on whether you're running from Visual Studio:</span></span>

- <span data-ttu-id="5361d-128">Wenn Sie **nicht** Visual Studio verwenden, lautet der Standardwert `true`.</span><span class="sxs-lookup"><span data-stu-id="5361d-128">If you're **not** in Visual Studio, the default value is `true`.</span></span>
- <span data-ttu-id="5361d-129">Wenn Sie Visual Studio verwenden, wird der angeforderte Status der Vorabversion verwendet.</span><span class="sxs-lookup"><span data-stu-id="5361d-129">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="5361d-130">Das bedeutet, dass bei der Verwendung einer Vorabversion von Visual Studio oder beim Festlegen der Option **Vorschauversionen des .NET Core SDK verwenden** (unter **Extras** > **Optionen** > **Umgebung** > **Preview Features** (Vorschaufeatures)) der Standardwert `true` verwendet wird. Ansonsten wird der Wert `false` verwendet.</span><span class="sxs-lookup"><span data-stu-id="5361d-130">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features** ), the default value is `true`; otherwise, `false`.</span></span>

#### <a name="rollforward"></a><span data-ttu-id="5361d-131">rollForward</span><span class="sxs-lookup"><span data-stu-id="5361d-131">rollForward</span></span>

- <span data-ttu-id="5361d-132">Typ: `string`</span><span class="sxs-lookup"><span data-stu-id="5361d-132">Type: `string`</span></span>

- <span data-ttu-id="5361d-133">Verfügbar seit dem .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="5361d-133">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="5361d-134">Die Rollforwardrichtlinie, die beim Auswählen einer SDK-Version verwendet werden soll, entweder als Fallback, wenn eine bestimmte SDK-Version fehlt, oder als Anweisung, damit eine höhere Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5361d-134">The roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span> <span data-ttu-id="5361d-135">Eine [Version](#version) muss mit einem `rollForward`-Wert angegeben werden, wenn sie nicht auf `latestMajor` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5361d-135">A [version](#version) must be specified with a `rollForward` value, unless you're setting it to `latestMajor`.</span></span>
<span data-ttu-id="5361d-136">Das standardmäßige Verhalten beim Rollforward wird von den [Abgleichsregeln](#matching-rules) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="5361d-136">The default roll forward behavior is determined by the [matching rules](#matching-rules).</span></span>

<span data-ttu-id="5361d-137">Lesen Sie sich die folgenden Definitionen für SDK-Versionen im Format `x.y.znn` durch, um sich ein Bild von den verfügbaren Richtlinien und deren Verhalten zu machen.</span><span class="sxs-lookup"><span data-stu-id="5361d-137">To understand the available policies and their behavior, consider the following definitions for an SDK version in the format `x.y.znn`:</span></span>

- <span data-ttu-id="5361d-138">`x` ist die Hauptversion.</span><span class="sxs-lookup"><span data-stu-id="5361d-138">`x` is the major version.</span></span>
- <span data-ttu-id="5361d-139">`y` ist die Nebenversion.</span><span class="sxs-lookup"><span data-stu-id="5361d-139">`y` is the minor version.</span></span>
- <span data-ttu-id="5361d-140">`z` ist die Featuregruppe.</span><span class="sxs-lookup"><span data-stu-id="5361d-140">`z` is the feature band.</span></span>
- <span data-ttu-id="5361d-141">`nn` ist die Patchversion.</span><span class="sxs-lookup"><span data-stu-id="5361d-141">`nn` is the patch version.</span></span>

<span data-ttu-id="5361d-142">In der folgenden Tabelle werden die verschiedenen möglichen Werte für den Schlüssel `rollForward` angezeigt:</span><span class="sxs-lookup"><span data-stu-id="5361d-142">The following table shows the possible values for the `rollForward` key:</span></span>

| <span data-ttu-id="5361d-143">Wert</span><span class="sxs-lookup"><span data-stu-id="5361d-143">Value</span></span>         | <span data-ttu-id="5361d-144">Verhalten</span><span class="sxs-lookup"><span data-stu-id="5361d-144">Behavior</span></span> |
| ------------- | ---------- |
| `patch`       | <span data-ttu-id="5361d-145">Verwendet die angegebene Version.</span><span class="sxs-lookup"><span data-stu-id="5361d-145">Uses the specified version.</span></span> <br> <span data-ttu-id="5361d-146">Wenn dieser Wert nicht gefunden wird, wird ein Rollforward auf die neuste Patchebene ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5361d-146">If not found, rolls forward to the latest patch level.</span></span> <br> <span data-ttu-id="5361d-147">Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5361d-147">If not found, fails.</span></span> <br><br> <span data-ttu-id="5361d-148">Dieser Wert steht für das Legacyverhalten aus früheren Versionen des SDK.</span><span class="sxs-lookup"><span data-stu-id="5361d-148">This value is the legacy behavior from the earlier versions of the SDK.</span></span> |
| `feature`     | <span data-ttu-id="5361d-149">Verwendet die aktuelle Patchebene für die angegebene Haupt- und Nebenversion sowie die angegebene Featuregruppe.</span><span class="sxs-lookup"><span data-stu-id="5361d-149">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="5361d-150">Wenn dieser Wert nicht gefunden wird, wird eine Rollforward auf die nächsthöhere Featuregruppe innerhalb derselben Haupt- bzw. Nebenversion ausgeführt, und es wird die neuste Patchebene für diese Featuregruppe verwendet.</span><span class="sxs-lookup"><span data-stu-id="5361d-150">If not found, rolls forward to the next higher feature band within the same major/minor and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="5361d-151">Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5361d-151">If not found, fails.</span></span> |
| `minor`       | <span data-ttu-id="5361d-152">Verwendet die aktuelle Patchebene für die angegebene Haupt- und Nebenversion sowie die angegebene Featuregruppe.</span><span class="sxs-lookup"><span data-stu-id="5361d-152">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="5361d-153">Wenn dieser Wert nicht gefunden wird, wird ein Rollforward auf die nächsthöhere Featuregruppe innerhalb derselben Haupt- bzw. Nebenversion ausgeführt, und es wird die neuste Patchebene für diese Featuregruppe verwendet.</span><span class="sxs-lookup"><span data-stu-id="5361d-153">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="5361d-154">Wenn dieser Wert nicht gefunden wird, wird eine Rollforward auf die nächsthöhere Nebenversion und die nächsthöhere Featuregruppe innerhalb derselben Hauptversion ausgeführt, und es wird die neuste Patchebene für diese Featuregruppe verwendet.</span><span class="sxs-lookup"><span data-stu-id="5361d-154">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="5361d-155">Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5361d-155">If not found, fails.</span></span> |
| `major`       | <span data-ttu-id="5361d-156">Verwendet die aktuelle Patchebene für die angegebene Haupt- und Nebenversion sowie die angegebene Featuregruppe.</span><span class="sxs-lookup"><span data-stu-id="5361d-156">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="5361d-157">Wenn dieser Wert nicht gefunden wird, wird ein Rollforward auf die nächsthöhere Featuregruppe innerhalb derselben Haupt- bzw. Nebenversion ausgeführt, und es wird die neuste Patchebene für diese Featuregruppe verwendet.</span><span class="sxs-lookup"><span data-stu-id="5361d-157">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="5361d-158">Wenn dieser Wert nicht gefunden wird, wird eine Rollforward auf die nächsthöhere Nebenversion und die nächsthöhere Featuregruppe innerhalb derselben Hauptversion ausgeführt, und es wird die neuste Patchebene für diese Featuregruppe verwendet.</span><span class="sxs-lookup"><span data-stu-id="5361d-158">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="5361d-159">Wenn dieser Wert nicht gefunden wird, wird eine Rollforward auf die nächsthöhere Haupt-, Nebenversion und Featuregruppe ausgeführt, und es wird die neuste Patchebene für diese Featuregruppe verwendet.</span><span class="sxs-lookup"><span data-stu-id="5361d-159">If not found, rolls forward to the next higher major, minor, and feature band and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="5361d-160">Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5361d-160">If not found, fails.</span></span> |
| `latestPatch` | <span data-ttu-id="5361d-161">Verwendet die neuste installierte Patchebene, die mit der angeforderten Haupt-, Nebenversion und Featuregruppe mit einer Patchebene übereinstimmt und größer als der angegebene Wert ist oder diesem entspricht.</span><span class="sxs-lookup"><span data-stu-id="5361d-161">Uses the latest installed patch level that matches the requested major, minor, and feature band with a patch level and that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="5361d-162">Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5361d-162">If not found, fails.</span></span> |
| `latestFeature` | <span data-ttu-id="5361d-163">Verwendet die höchste installierte Featuregruppe und Patchebene, die mit der angeforderten Haupt- und Nebenversion mit einer Featuregruppe und einer Patchebene übereinstimmt, die größer als der angegebene Wert ist oder diesem entspricht.</span><span class="sxs-lookup"><span data-stu-id="5361d-163">Uses the highest installed feature band and patch level that matches the requested major and minor with a feature band and patch level that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="5361d-164">Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5361d-164">If not found, fails.</span></span> |
| `latestMinor` | <span data-ttu-id="5361d-165">Verwendet die höchste installierte Nebenversion, Featuregruppe und Patchebene, die mit der angeforderten Hauptversion mit einer Nebenversion, einer Featuregruppe und einer Patchebene übereinstimmt, die größer als der angegebene Wert ist oder diesem entspricht.</span><span class="sxs-lookup"><span data-stu-id="5361d-165">Uses the highest installed minor, feature band, and patch level that matches the requested major with a minor, feature band, and patch level that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="5361d-166">Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5361d-166">If not found, fails.</span></span> |
| `latestMajor` | <span data-ttu-id="5361d-167">Verwendet das höchste installierte .NET Core SDK mit einer Version, die größer als der angegebene Wert ist oder diesem entspricht.</span><span class="sxs-lookup"><span data-stu-id="5361d-167">Uses the highest installed .NET Core SDK with a version that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="5361d-168">Wenn dieser Wert nicht gefunden wird, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5361d-168">If not found, fail.</span></span> |
| `disable`     | <span data-ttu-id="5361d-169">Es wird kein Rollforward ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5361d-169">Doesn't roll forward.</span></span> <span data-ttu-id="5361d-170">Es ist eine exakte Übereinstimmung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5361d-170">Exact match required.</span></span> |

### <a name="msbuild-sdks"></a><span data-ttu-id="5361d-171">msbuild-sdks</span><span class="sxs-lookup"><span data-stu-id="5361d-171">msbuild-sdks</span></span>

<span data-ttu-id="5361d-172">Typ: `object`</span><span class="sxs-lookup"><span data-stu-id="5361d-172">Type: `object`</span></span>

<span data-ttu-id="5361d-173">Ermöglicht Ihnen die Kontrolle der SDK-Version des Projekts an einem einzigen Ort anstatt in jedem Projekt einzeln.</span><span class="sxs-lookup"><span data-stu-id="5361d-173">Lets you control the project SDK version in one place rather than in each individual project.</span></span> <span data-ttu-id="5361d-174">Weitere Informationen finden Sie unter [Lösen von Projekt SDKs](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved).</span><span class="sxs-lookup"><span data-stu-id="5361d-174">For more information, see [How project SDKs are resolved](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved).</span></span>

## <a name="examples"></a><span data-ttu-id="5361d-175">Beispiele</span><span class="sxs-lookup"><span data-stu-id="5361d-175">Examples</span></span>

<span data-ttu-id="5361d-176">Das folgende Beispiel zeigt, wie Sie verhindern können, dass Vorabversionen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="5361d-176">The following example shows how to not use prerelease versions:</span></span>

```json
{
  "sdk": {
    "allowPrerelease": false
  }
}
```

<span data-ttu-id="5361d-177">Im folgenden Beispiel wird gezeigt, wie Sie festlegen können, dass die höchste installierte Version verwendet wird, die höher als die angegebene Version ist oder dieser entspricht.</span><span class="sxs-lookup"><span data-stu-id="5361d-177">The following example shows how to use the highest version installed that is greater or equal than the specified version.</span></span> <span data-ttu-id="5361d-178">Der gezeigte JSON-Code lässt keine niedrigere SDK-Version als 2.2.200 zu und lässt 2.2.200 oder jede höhere Version zu, einschließlich 3.0.xxx und 3.1.xxx.</span><span class="sxs-lookup"><span data-stu-id="5361d-178">The JSON shown disallows any SDK version earlier than 2.2.200 and allows 2.2.200 or any later version, including 3.0.xxx and 3.1.xxx.</span></span>

```json
{
  "sdk": {
    "version": "2.2.200",
    "rollForward": "latestMajor"
  }
}
```

<span data-ttu-id="5361d-179">Das folgende Beispiel zeigt, wie Sie festlegen können, welche genaue Version verwendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="5361d-179">The following example shows how to use the exact specified version:</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "disable"
  }
}
```

<span data-ttu-id="5361d-180">Das folgende Beispiel zeigt, wie das neueste Featureband und die neueste Patchversion verwendet werden, die von einer bestimmten Haupt- und Nebenversion installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5361d-180">The following example shows how to use the latest feature band and patch version installed of a specific major and minor version.</span></span> <span data-ttu-id="5361d-181">Der gezeigte JSON-Code lässt keine niedrigere SDK-Version als 3.1.102 zu und lässt 3.1.102 oder jede höhere 3.1.xxx-Version zu, z. B. 3.1.103 oder 3.1.200.</span><span class="sxs-lookup"><span data-stu-id="5361d-181">The JSON shown disallows any SDK version earlier than 3.1.102 and allows 3.1.102 or any later 3.1.xxx version, such as 3.1.103 or 3.1.200.</span></span>

```json
{
  "sdk": {
    "version": "3.1.102",
    "rollForward": "latestFeature"
  }
}
```

<span data-ttu-id="5361d-182">Im folgenden Beispiel wird gezeigt, wie Sie festlegen können, dass die höchste installierte Patchversion einer bestimmten Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5361d-182">The following example shows how to use the highest patch version installed of a specific version.</span></span> <span data-ttu-id="5361d-183">Der gezeigte JSON-Code lässt keine niedrigere SDK-Version als 3.1.102 zu und lässt 3.1.102 oder jede höhere 3.1.1xx-Version zu, z. B. 3.1.103 oder 3.1.199.</span><span class="sxs-lookup"><span data-stu-id="5361d-183">The JSON shown disallows any SDK version earlier than 3.1.102 and allows 3.1.102 or any later 3.1.1xx version, such as 3.1.103 or 3.1.199.</span></span>

```json
{
  "sdk": {
    "version": "3.1.102",
    "rollForward": "latestPatch"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a><span data-ttu-id="5361d-184">global.json und die .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="5361d-184">global.json and the .NET Core CLI</span></span>

<span data-ttu-id="5361d-185">Sie sollten sich darüber informieren, welche SDK-Versionen auf Ihrem Computer installiert sind, um auch in Ihrer *global.json* -Datei eine Version festzulegen.</span><span class="sxs-lookup"><span data-stu-id="5361d-185">It's helpful to know which SDK versions are installed on your machine to set one in the *global.json* file.</span></span> <span data-ttu-id="5361d-186">Weitere Informationen dazu finden Sie unter [Überprüfen, ob .NET Core bereits installiert ist](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span><span class="sxs-lookup"><span data-stu-id="5361d-186">For more information on how to do that, see [How to check that .NET Core is already installed](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span></span>

<span data-ttu-id="5361d-187">Weitere .NET Core SDK-Versionen, die Sie auf Ihrem Computer installieren können, finden Sie unter [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="5361d-187">To install additional .NET Core SDK versions on your machine, visit the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>

<span data-ttu-id="5361d-188">Sie können im aktuellen Verzeichnis eine neue *global.json* -Datei erstellen, indem Sie den Befehl [dotnet new](dotnet-new.md) ausführen, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5361d-188">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```dotnetcli
dotnet new globaljson --sdk-version 3.0.100
```

## <a name="matching-rules"></a><span data-ttu-id="5361d-189">Abgleichsregeln</span><span class="sxs-lookup"><span data-stu-id="5361d-189">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="5361d-190">Die Abgleichsregeln werden vom Einstiegspunkt `dotnet.exe` geregelt, der für alle installierten .NET Core-Runtimes gleich ist.</span><span class="sxs-lookup"><span data-stu-id="5361d-190">The matching rules are governed by the `dotnet.exe` entry point, which is common across all installed .NET Core installed runtimes.</span></span> <span data-ttu-id="5361d-191">Die Abgleichsregeln für die neuste installierte Version der .NET Core-Runtime werden verwendet, wenn mehrere Runtimes parallel installiert sind oder Sie die Datei *global.json* verwenden.</span><span class="sxs-lookup"><span data-stu-id="5361d-191">The matching rules for the latest installed version of the .NET Core Runtime are used when you have multiple runtimes installed side-by-side or if or you're using a *global.json* file.</span></span>

## <a name="net-core-3x"></a>[<span data-ttu-id="5361d-192">.NET Core 3.x</span><span class="sxs-lookup"><span data-stu-id="5361d-192">.NET Core 3.x</span></span>](#tab/netcore3x)

<span data-ttu-id="5361d-193">Ab .NET Core 3.0 gelten die folgenden Regeln, wenn ermittelt wird, welche SDK-Version verwendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="5361d-193">Starting with .NET Core 3.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="5361d-194">Wenn keine *global.json* -Datei gefunden wird oder in der *global.json* -Datei weder eine SDK-Version noch ein `allowPrerelease`-Wert angegeben wird, wird die höchste installierte SDK-Version verwendet (entspricht dem Festlegen von `rollForward` auf `latestMajor`).</span><span class="sxs-lookup"><span data-stu-id="5361d-194">If no *global.json* file is found, or *global.json* doesn't specify an SDK version nor an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="5361d-195">Ob Vorabversionen von SDKs berücksichtigt werden, ist davon abhängig, wie `dotnet` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5361d-195">Whether prerelease SDK versions are considered depends on how `dotnet` is being invoked.</span></span>
  - <span data-ttu-id="5361d-196">Wenn Sie **nicht** Visual Studio verwenden, werden Vorabversionen berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5361d-196">If you're **not** in Visual Studio, prerelease versions are considered.</span></span>
  - <span data-ttu-id="5361d-197">Wenn Sie Visual Studio verwenden, wird der angeforderte Status der Vorabversion verwendet.</span><span class="sxs-lookup"><span data-stu-id="5361d-197">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="5361d-198">Das bedeutet, dass bei der Verwendung einer Vorabversion von Visual Studio oder beim Festlegen der Option **Vorschauversionen des .NET Core SDK verwenden** (unter **Extras** > **Optionen** > **Umgebung** > **Preview Features** (Vorschaufeatures)) Vorabversionen berücksichtigt werden. Andernfalls werden nur Releaseversionen berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5361d-198">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features** ), prerelease versions are considered; otherwise, only release versions are considered.</span></span>
- <span data-ttu-id="5361d-199">Wenn eine *global.json* -Datei gefunden wird, in der keine SDK-Version, aber dafür ein `allowPrerelease`-Wert angegeben ist, wird die höchste installierte SDK-Version verwendet (entspricht dem Festlegen von `rollForward` auf `latestMajor`).</span><span class="sxs-lookup"><span data-stu-id="5361d-199">If a *global.json* file is found that doesn't specify an SDK version but it specifies an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="5361d-200">Ob es sich bei der neusten SDK-Version um ein Release handeln muss oder ob Vorabversionen akzeptiert werden, hängt vom Wert `allowPrerelease` ab.</span><span class="sxs-lookup"><span data-stu-id="5361d-200">Whether the latest SDK version can be release or prerelease depends on the value of `allowPrerelease`.</span></span> <span data-ttu-id="5361d-201">`true` gibt an, dass Vorabversionen berücksichtigt werden, während bei `false` nur Releases berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="5361d-201">`true` indicates prerelease versions are considered; `false` indicates that only release versions are considered.</span></span>
- <span data-ttu-id="5361d-202">Wenn eine *global.json* -Datei gefunden wird und in dieser eine SDK-Version angegeben ist, geschieht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5361d-202">If a *global.json* file is found and it specifies an SDK version:</span></span>

  - <span data-ttu-id="5361d-203">Wenn kein `rollForward`-Wert festgelegt ist, wird `latestPatch` als `rollForward`-Standardrichtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="5361d-203">If no `rollForward` value is set, it uses `latestPatch` as the default `rollForward` policy.</span></span> <span data-ttu-id="5361d-204">Überprüfen Sie andernfalls die einzelnen Werte und deren Verhalten im Abschnitt [rollForward](#rollforward).</span><span class="sxs-lookup"><span data-stu-id="5361d-204">Otherwise, check each value and their behavior in the [rollForward](#rollforward) section.</span></span>
  - <span data-ttu-id="5361d-205">Im Abschnitt [allowPrerelease](#allowprerelease) wird beschrieben, ob Vorabversionen berücksichtigt werden, und es wird das Standardverhalten festgelegt, wenn `allowPrerelease` nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5361d-205">Whether prerelease versions are considered and what's the default behavior when `allowPrerelease` isn't set is described in the [allowPrerelease](#allowprerelease) section.</span></span>

## <a name="net-core-2x"></a>[<span data-ttu-id="5361d-206">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="5361d-206">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="5361d-207">Im .NET Core 2.x SDK gelten die folgenden Regeln, wenn ermittelt wird, welche Version des SDK verwendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="5361d-207">In .NET Core 2.x SDK, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="5361d-208">Wenn keine *global.json* -Datei gefunden wird oder *global.json* keine SDK-Version angibt, wird die neueste installierte SDK-Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="5361d-208">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="5361d-209">Die neuste SDK-Version kann ein Release oder eine Vorabversion sein – es gilt die höchste Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="5361d-209">Latest SDK version can be either release or prerelease - the highest version number wins.</span></span>
- <span data-ttu-id="5361d-210">Wenn *global.json* eine SDK-Version angibt:</span><span class="sxs-lookup"><span data-stu-id="5361d-210">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="5361d-211">Wenn die angegebene SDK-Version auf dem Computer gefunden wird, wird genaue diese Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="5361d-211">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="5361d-212">Wenn die angegebene SDK-Version auf dem Computer nicht gefunden wird, wird die neueste installierte SDK- **Patchversion** der Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="5361d-212">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="5361d-213">Die neuste installierte SDK- **Patchversion** kann ein Release oder eine Vorabversion sein – es gilt die höchste Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="5361d-213">Latest installed SDK **patch version** can be either release or prerelease - the highest version number wins.</span></span> <span data-ttu-id="5361d-214">In .NET Core 2.1 und höher werden die **Patchversionen** , die niedriger als die angegebene **Patchversion** sind, bei der SDK-Auswahl ignoriert.</span><span class="sxs-lookup"><span data-stu-id="5361d-214">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="5361d-215">Wenn die angegebene SDK-Version und eine entsprechende SDK- **Patchversion** nicht gefunden werden, wird ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="5361d-215">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="5361d-216">Die SDK-Version hat folgende Bestandteile:</span><span class="sxs-lookup"><span data-stu-id="5361d-216">The SDK version is composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="5361d-217">Die **Funktionsfreigabe** von .NET Core SDK wird für SDK-Versionen ab 2.1.100 von der ersten Ziffer (`x`) im letzten Teil der Nummer (`xyz`) dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5361d-217">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="5361d-218">Generell hat .NET Core SDK einen schnelleren Releasezyklus als .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5361d-218">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="5361d-219">Die **Patchversion** wird für SDK-Versionen ab 2.1.100 von den letzten beiden Ziffern (`yz`) im letzten Teil der Nummer (`xyz`) definiert.</span><span class="sxs-lookup"><span data-stu-id="5361d-219">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="5361d-220">Wenn Sie beispielsweise `2.1.300` als SDK-Version angeben, werden für die SDK-Auswahl Versionen bis `2.1.399` berücksichtigt, allerdings wird `2.1.400` nicht als Patchversion von `2.1.300` betrachtet.</span><span class="sxs-lookup"><span data-stu-id="5361d-220">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="5361d-221">.NET Core SDK-Versionen `2.1.100` bis `2.1.201` wurden beim Übergang zwischen Versionsnummerschemen freigegeben und halten die `xyz`-Notation nicht ordnungsgemäß ein.</span><span class="sxs-lookup"><span data-stu-id="5361d-221">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="5361d-222">Falls Sie diese Versionen in der *global.json* -Datei angeben, wird dringend empfohlen sicherzustellen, dass sich die angegebenen Versionen auf den Zielcomputern befinden.</span><span class="sxs-lookup"><span data-stu-id="5361d-222">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

---

## <a name="troubleshoot-build-warnings"></a><span data-ttu-id="5361d-223">Problembehandlung bei Buildwarnungen</span><span class="sxs-lookup"><span data-stu-id="5361d-223">Troubleshoot build warnings</span></span>

* <span data-ttu-id="5361d-224">Die folgende Warnung weist darauf hin, dass das Projekt mit einer Vorabversion des .NET Core SDK kompiliert wurde:</span><span class="sxs-lookup"><span data-stu-id="5361d-224">The following warning indicates that your project was compiled using a prerelease version of the .NET Core SDK:</span></span>

  > <span data-ttu-id="5361d-225">Sie verwenden eine Vorschauversion von .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="5361d-225">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="5361d-226">Sie können die SDK-Version über eine global.json-Datei im aktuellen Projekt definieren.</span><span class="sxs-lookup"><span data-stu-id="5361d-226">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="5361d-227">Weitere Informationen finden Sie unter <https://go.microsoft.com/fwlink/?linkid=869452>.</span><span class="sxs-lookup"><span data-stu-id="5361d-227">More at <https://go.microsoft.com/fwlink/?linkid=869452>.</span></span>

  <span data-ttu-id="5361d-228">.NET Core SDK-Versionen haben einen Verlauf und weisen eine hohe Qualität auf.</span><span class="sxs-lookup"><span data-stu-id="5361d-228">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="5361d-229">Wenn Sie jedoch keine Vorabversion verwenden möchten, prüfen Sie im Abschnitt [allowPrerelease](#allowprerelease) die verschiedenen Strategien, die Sie mit dem .NET Core 3.0 SDK oder einer höheren Version verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5361d-229">However, if you don't want to use a prerelease version, check the different strategies you can use with the .NET Core 3.0 SDK or a later version in the [allowPrerelease](#allowprerelease) section.</span></span> <span data-ttu-id="5361d-230">Für Computer, auf denen eine Runtime oder ein SDK für .NET Core 3.0 oder höher installiert ist, benötigen Sie eine *global.json* -Datei und müssen die genaue Version angeben, die verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5361d-230">For machines that have never had a .NET Core 3.0 or higher Runtime or SDK installed, you need to create a *global.json* file and specify the exact version you want to use.</span></span>

* <span data-ttu-id="5361d-231">Die folgende Warnung gibt an, dass Ihr Projekt für EF Core 1.0 oder 1.1 ausgelegt ist. Diese Versionen sind nicht mit dem .NET Core 2.1 SDK und höheren Versionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="5361d-231">The following warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions:</span></span>

  > <span data-ttu-id="5361d-232">Das Startprojekt „{startupProject}“ gibt Version „{targetFrameworkVersion}“ von Framework „.NETCoreApp“ als Ziel an.</span><span class="sxs-lookup"><span data-stu-id="5361d-232">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="5361d-233">Diese Version der Entity Framework Core .NET-Befehlszeilentools unterstützt nur Version 2.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="5361d-233">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="5361d-234">Weitere Informationen zur Verwendung älterer Toolversionen finden Sie unter <https://go.microsoft.com/fwlink/?linkid=871254>.</span><span class="sxs-lookup"><span data-stu-id="5361d-234">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254>.</span></span>

  <span data-ttu-id="5361d-235">Ab .NET Core 2.1 SDK (Version 2.1.300) ist der Befehl `dotnet ef` im SDK enthalten.</span><span class="sxs-lookup"><span data-stu-id="5361d-235">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="5361d-236">Installieren Sie das .NET Core 2.0 SDK (Version 2.1.201) oder früher auf Ihrem Computer, und definieren Sie die gewünschte Version des SDKs mithilfe der Datei *global.json* , um Ihr Projekt zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="5361d-236">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) or earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="5361d-237">Weitere Informationen zu dem Befehl `dotnet ef` finden Sie unter [EF Core .NET-Befehlszeilentools](/ef/core/miscellaneous/cli/dotnet).</span><span class="sxs-lookup"><span data-stu-id="5361d-237">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="5361d-238">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5361d-238">See also</span></span>

- [<span data-ttu-id="5361d-239">Wie Projekt-SDKs gelöst werden</span><span class="sxs-lookup"><span data-stu-id="5361d-239">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
