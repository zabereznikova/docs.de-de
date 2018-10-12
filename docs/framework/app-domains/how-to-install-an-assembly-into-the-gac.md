---
title: Installieren einer Assembly im globalen Assemblycache
ms.date: 09/20/2018
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d365ac77fe6cd7fc4fca36705729ec12b06d6830
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2018
ms.locfileid: "46584580"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Gewusst wie: Installieren einer Assembly im globalen Assemblycache

Es gibt zwei Möglichkeiten, eine Assembly mit starkem Namen im globalen Assemblycache (GAC) zu installieren.

> [!IMPORTANT]
> Nur Assemblys mit starkem Namen können im GAC installiert werden. Informationen zum Erstellen einer Assembly mit starkem Namen finden Sie unter [How to: Sign an Assembly with a Strong Name (Vorgehensweise: Signieren einer Assembly mit einem starken Namen)](how-to-sign-an-assembly-with-a-strong-name.md).

## <a name="windows-installer"></a>Windows Installer

[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), das Windows-Installationsmodul, stellt das empfohlene Verfahren zum Hinzufügen von Assemblys zum globalen Assemblycache dar. Der Windows Installer bietet neben einem Verweiszähler für Assemblys im globalen Assemblycache noch weitere Vorteile. Sie können die [WiX-Toolseterweiterung für Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension) verwenden, um ein Installationspaket für Windows Installer zu erstellen.

## <a name="global-assembly-cache-tool"></a>Globaler Assemblycache-Tool

Mit dem [Globaler Assemblycache-Tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) können Sie Assemblys mit starkem Namen zum globalen Assemblycache hinzufügen und sich dessen Inhalt anzeigen lassen.

   > [!NOTE]
   > Gacutil.exe ist Entwicklungszwecken vorbehalten und nicht für die Installation von Produktionsassemblys im globalen Assemblycache vorgesehen.

Die Syntax für gacutil lautet wie folgt:

```shell
gacutil -i <assembly name>
```

In diesem Befehl bezeichnet *Assemblyname* den Namen der Assembly, die im globalen Assemblycache installiert werden soll.

Im folgenden Beispiel wird eine Assembly mit dem Dateinamen `hello.dll` im globalen Assemblycache installiert.

```shell
gacutil -i hello.dll
```

> [!NOTE]
> In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung „Shfusion.dll“ das Installieren von Assemblys durch Ziehen in **Datei-Explorer**. Seit .NET Framework 4 ist Shfusion.dll veraltet.

## <a name="see-also"></a>Siehe auch

- [Arbeiten mit Assemblys und dem globalen Assemblychache](working-with-assemblies-and-the-gac.md)
- [Gewusst wie: Entfernen einer Assembly aus dem globalen Assemblycache](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (Global Assembly Cache-Tool)](../tools/gacutil-exe-gac-tool.md)
- [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](how-to-sign-an-assembly-with-a-strong-name.md)