---
title: Laden von Abhängigkeiten – .NET Core
description: Übersicht über das verwaltete und nicht verwaltete Laden von Abhängigkeiten in .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.topic: overview
ms.openlocfilehash: 34deb802183f20cc92449c21eb7e149cc002850f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284221"
---
# <a name="dependency-loading-in-net-core"></a>Laden von Abhängigkeiten in .NET Core

Jede .NET Core-Anwendung weist Abhängigkeiten auf. Selbst die einfache `hello world`-App wiest Abhängigkeiten von Teilen der .NET Core-Klassenbibliotheken auf.

Das Verständnis der Logik hinter dem Laden von .NET Core-Standardassemblys kann beim Verstehen und Debuggen gängiger Bereitstellungsprobleme helfen.

In einigen Anwendungen werden Abhängigkeiten dynamisch zur Laufzeit festgelegt. In diesen Fällen ist es wichtig zu verstehen, wie verwaltete Assemblys und nicht verwaltete Abhängigkeiten geladen werden.

## <a name="understanding-assemblyloadcontext"></a>Grundlegendes zu AssemblyLoadContext

Die <xref:System.Runtime.Loader.AssemblyLoadContext>-API ist für das Laden in .NET Core von zentraler Bedeutung. Der Artikel [Grundlegendes zu AssemblyLoadContext](understanding-assemblyloadcontext.md) enthält eine konzeptionelle Übersicht über den Entwurf.

## <a name="loading-details"></a>Laden von Details

Details zum Ladealgorithmus werden in mehreren Artikeln kurz behandelt:

- [Ladealgorithmus für verwaltete Assemblys](loading-managed.md)
- [Ladealgorithmus für Satellitenassemblys](loading-resources.md)
- [Ladealgorithmus für nicht verwaltete (native) Bibliotheken](loading-unmanaged.md)
- [Standardüberprüfung](default-probing.md)

## <a name="create-a-net-core-application-with-plugins"></a>Erstellen einer .NET Core-Anwendung mit Plug-Ins

Im Tutorial [Erstellen einer .NET Core-Anwendung mit Plug-Ins](../tutorials/creating-app-with-plugin-support.md) wird beschrieben, wie ein benutzerdefinierter AssemblyLoadContext erstellt wird. Er verwendet einen <xref:System.Runtime.Loader.AssemblyDependencyResolver>, um die Abhängigkeiten des Plug-Ins aufzulösen. Das Tutorial isoliert die Plug-In-Abhängigkeiten ordnungsgemäß von der Hostanwendung.

## <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a>Verwenden und Debuggen von Assemblyentladbarkeit in .NET Core

Der Artikel [Verwenden und Debuggen der Entladbarkeit von Assemblys in .NET Core](../../standard/assembly/unloadability.md) enthält ein ausführliches Tutorial. Darin wird gezeigt, wie Sie eine .NET Core-Anwendung laden, ausführen und dann entladen. Der Artikel enthält auch Tipps zum Debuggen.
