---
title: Zuschneiden eigenständiger Anwendungen
description: Erfahren Sie, wie Sie eigenständige Apps zuschneiden, um ihre Größe zu verringern. .NET Core bündelt die Laufzeit mit einer App, die eigenständig veröffentlicht wird und deren Laufzeit in der Regel umfangreicher als erforderlich ist.
author: jamshedd
ms.author: jamshedd
ms.date: 01/23/2020
ms.openlocfilehash: 5206ca255c500b382402ac4e7dd3300b7face1cf
ms.sourcegitcommit: 45cced471d59d5dac3f0c92abc9d4849716098a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/04/2020
ms.locfileid: "80665620"
---
# <a name="trim-self-contained-deployments-and-executables"></a>Kürzen eigenständiger Bereitstellungen und ausführbarer Dateien

Beim Veröffentlichen einer eigenständigen Anwendung wird die .NET Core-Laufzeit mit der Anwendung gebündelt. Durch diese Bündelung wird die Menge des Inhalts der gepackten Anwendung beträchtlich erhöht.

Wenn Sie Ihre Anwendung bereitstellen, ist die Größe häufig ein wichtiger Faktor. Anwendungsentwickler versuchen in der Regel, die Größe des Anwendungspakets so gering wie möglich zu halten.

Abhängig von der Komplexität der Anwendung ist für ihre Ausführung nur eine Teilmenge der Laufzeit erforderlich. Diese nicht verwendeten Teile der Laufzeit sind unnötig und können aus der gepackten Anwendung abgeschnitten werden.

> [!NOTE]
> Das Kürzen ist ein experimentelles Feature in .NET Core 3.1 und _nur_ für Anwendungen verfügbar, die eigenständig veröffentlicht werden.

## <a name="trim-your-application"></a>Kürzen der Anwendung

Im folgenden Beispiel wird gezeigt, wie Sie die Anwendung mit dem Befehl [dotnet publish](../tools/dotnet-publish.md) kürzen:

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true /p:PublishSingleFile=false /p:PublishTrimmed=true
```

Zum Kürzen der Anwendung werden ihre Binärdateien untersucht, um die erforderlichen Laufzeitassemblys zu ermitteln und einen entsprechenden Graphen zu erstellen. Die verbleibenden Laufzeitassemblys, auf die nicht verwiesen wird, werden abgeschnitten.

## <a name="trimming-issues-when-using-reflection"></a>Kürzungsprobleme bei Verwendung von Spiegelung

In manchen Szenarien schlägt das Ermitteln von Verweisen durch die Kürzungsfunktion fehl. Beispielsweise kann dieses Problem bei einer Anwendung auftreten, die Spiegelung verwendet, da die Abhängigkeit von der Assembly nur zur Laufzeit bekannt ist.

Das Kürzen ist nur problematisch, wenn die Verwendung von Spiegelung von einer Laufzeitassembly abhängt, auf die nicht direkt verwiesen wird. Beachten Sie, dass im Anwendungscode möglicherweise Spiegelung nicht direkt verwendet wird, diese jedoch von einer Drittanbieterassembly verwendet wird, auf die Sie verweisen.

Wenn der Code über Spiegelung auf eine API verweist und der Linker die Assembly nicht kürzen soll, die diese API enthält, können Sie die Projektdatei ändern, um die Assembly aus dem Kürzungsvorgang auszuschließen. Im folgenden Beispiel wird gezeigt, wie das Kürzen einer Assembly mit dem Namen `System.Security` verhindert wird:

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="see-also"></a>Siehe auch

- [.NET Core-Anwendungsbereitstellung](index.md)
