---
title: 'Vorgehensweise: Installieren einer Assembly im globalen Assemblycache'
description: Installieren Sie eine Assembly im globalen Assemblycache (Global Assembly Cache, GAC) in .NET, damit sie von mehreren Anwendungen gemeinsam genutzt werden kann. Verwenden Sie den Windows Installer oder das GAC-Hilfsprogramm.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
ms.openlocfilehash: 08a5475d74327265f28b65676ae56be15afb57d3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104668"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Vorgehensweise: Installieren einer Assembly im globalen Assemblycache

Im globalen Assemblycache (GAC) werden Assemblys gespeichert, die von mehreren Anwendungen gemeinsam verwendet werden. Installieren Sie eine Assembly mit einer der folgenden Komponenten in den [globalen Assemblycache](gac.md):

- [Windows Installer](#windows-installer)
- [Tool für globalen Assemblycache](#global-assembly-cache-tool)

> [!IMPORTANT]
> Sie können nur Assemblys mit starkem Namen im globalen Assemblycache installieren. Informationen zum Erstellen von Assemblys mit starkem Namen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../standard/assembly/sign-strong-name.md).

## <a name="windows-installer"></a>Windows Installer

[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), das Windows-Installationsmodul, stellt das empfohlene Verfahren zum Hinzufügen von Assemblys zum globalen Assemblycache dar. Der Windows Installer bietet neben einem Verweiszähler für Assemblys im globalen Assemblycache noch weitere Vorteile. Verwenden Sie die [WiX-Toolseterweiterung für Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension), um ein Installationspaket für Windows Installer zu erstellen.

## <a name="global-assembly-cache-tool"></a>Tool für globalen Assemblycache

Mit dem [.NET-Hilfsprogramm für den globalen Assemblycache (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) können Sie dem globalen Assemblycache Assemblys hinzufügen und sich dessen Inhalt anzeigen lassen.

   > [!NOTE]
   > Die *gacutil.exe* ist nur für Entwicklungszwecke vorgesehen. Verwenden Sie die ausführbare Datei nicht zum Installieren von Produktionsassemblys in den globalen Assemblycache.

Die Syntax zur Verwendung der *gacutil.exe* zum Installieren einer Assembly im GAC lautet wie folgt:

```cmd
gacutil -i <assembly name>
```

In diesem Befehl bezeichnet *\<assembly name>* den Namen der Assembly, die im globalen Assemblycache installiert werden soll.

Wenn *gacutil.exe* sich nicht auf Ihrem Systempfad befindet, verwenden Sie die [Developer-Eingabeaufforderung für Visual Studio *\<version>* ](../tools/developer-command-prompt-for-vs.md).

Im folgenden Beispiel wird eine Assembly mit dem Dateinamen *hello.dll* im globalen Assemblycache installiert.

```cmd
gacutil -i hello.dll
```

> [!NOTE]
> In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung *Shfusion.dll* das Installieren von Assemblys durch Verschieben in den Datei-Explorer. Die *Shfusion.dll* ist seit .NET Framework 4 veraltet.

## <a name="see-also"></a>Siehe auch

- [Arbeiten mit Assemblys und dem globalen Assemblycache](working-with-assemblies-and-the-gac.md)
- [How to: Entfernen einer Assembly aus dem globalen Assemblycache](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (Tool für globalen Assemblycache)](../tools/gacutil-exe-gac-tool.md)
- [How to: Signieren einer Assembly mit einem starken Namen](../../standard/assembly/sign-strong-name.md)
