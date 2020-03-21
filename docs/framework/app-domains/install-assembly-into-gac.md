---
title: 'Gewusst wie: Installieren einer Assembly im globalen Assemblycache'
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
ms.openlocfilehash: 64878a795a7c5b790c8991064e32b82505685c0c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155562"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a>Gewusst wie: Installieren einer Assembly im globalen Assemblycache

Im globalen Assemblycache (GAC) werden Assemblys gespeichert, die von mehreren Anwendungen gemeinsam verwendet werden. Installieren Sie eine Assembly mit einer der folgenden Komponenten in den [globalen Assemblycache](gac.md):

- [Windows Installer](#windows-installer)
- [Tool für globalen Assemblycache](#global-assembly-cache-tool)

> [!IMPORTANT]
> Sie können nur Assemblys mit starkem Namen im globalen Assemblycache installieren. Informationen zum Erstellen einer Assembly mit starkem Namen finden Sie unter [Gewusst wie: Signieren einer Assembly mit einem starken Namen](../../standard/assembly/sign-strong-name.md).

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

In diesem Befehl ist * \<assemblyname>* der Name der Assembly, die im globalen Assemblycache installiert werden soll.

Wenn *gacutil.exe* nicht in Ihrem Systempfad ist, verwenden Sie die [Eingabeaufforderung entwicklerfür * \<VS-Version>* ](../tools/developer-command-prompt-for-vs.md).

Im folgenden Beispiel wird eine Assembly mit dem Dateinamen *hello.dll* im globalen Assemblycache installiert.

```cmd
gacutil -i hello.dll
```

> [!NOTE]
> In früheren Versionen von .NET Framework ermöglichte die Windows Shell-Erweiterung *Shfusion.dll* das Installieren von Assemblys durch Verschieben in den Datei-Explorer. Die *Shfusion.dll* ist seit .NET Framework 4 veraltet.

## <a name="see-also"></a>Weitere Informationen

- [Arbeiten mit Assemblys und dem globalen Assemblycache](working-with-assemblies-and-the-gac.md)
- [Gewusst wie: Entfernen einer Assembly aus dem globalen Assemblycache](how-to-remove-an-assembly-from-the-gac.md)
- [Gacutil.exe (Global Assembly Cache-Tool)](../tools/gacutil-exe-gac-tool.md)
- [Gewusst wie: Signieren einer Assembly mit einem starken Namen](../../standard/assembly/sign-strong-name.md)
