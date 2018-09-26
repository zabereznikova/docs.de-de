---
title: Plattformübergreifende Entwicklung mit der portablen Klassenbibliothek
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
author: mairaw
ms.author: mairaw
ms.openlocfilehash: afaa8e118bb21e5c1e4f1c53b1d0d29ca6bb3bf5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47172705"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a>Plattformübergreifende Entwicklung mit der portablen Klassenbibliothek

Der Typ des Portable Class Library-Projekt in Visual Studio können Sie plattformübergreifende apps und Bibliotheken für Microsoft-Plattformen schnell und einfach zu erstellen.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

Portable Klassenbibliotheken können den Zeit- und Kostenaufwand für die Entwicklung und das Testen von Code verringern. Verwenden Sie diesen Projekttyp, schreiben und erstellen portabler .NET Framework-Assemblys und verweisen Sie dann diese Assemblys von apps für mehrere Plattformen wie .NET Framework, iOS oder Mac.

Auch nachdem Sie ein Projekt für eine portable Klassenbibliothek in Visual Studio erstellt haben und mit dem Entwickeln beginnen, können Sie die Zielplattformen noch ändern. Visual Studio kompiliert Ihre Bibliothek mit den neuen Assemblys verwenden, können Sie die Änderungen zu identifizieren, die Sie in Ihrem Code vornehmen müssen.

## <a name="create-a-portable-class-library-project"></a>Erstellen eines Portable Class Library-Projekts

Um eine Portable Klassenbibliothek zu erstellen, verwenden Sie die Vorlage in Visual Studio bereitgestellt. Erstellen eines neuen Projekts (**Datei** > **neues Projekt**), und klicken Sie in der **neues Projekt** Dialogfeld Wählen Ihre bevorzugte Programmiersprache (Visual c# oder Visual Basic). Wählen Sie dann die **Class-Bibliothek (Legacy-portabel)** Vorlage. Geben Sie einen Namen für Ihr Projekt, und wählen Sie **OK**.

Die **Portable Klassenbibliothek hinzufügen** Dialogfeld wird angezeigt. Wählen Sie mindestens zwei Ziele, und wählen Sie dann **OK**.

![Hinzufügen der portablen bibliotheksziele in Visual Studio](media/add-portable-class-library.png)

## <a name="change-targets"></a>Ziele ändern

Bei der Erstellung oder nachdem Sie die Entwicklung begonnen haben, können Sie die Zielplattformen, der ein portable Class Library-Projekt ändern. Wenn Sie die Zielplattformen ändern, nachdem Sie Ihrem Projekt, im erstellt haben möchten **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für das Portable Class Library-Projekt (nicht auf die Projektmappe), und wählen Sie dann **Eigenschaften** . Auf der Eigenschaftenseite des Projekts das **Bibliothek** Registerkarte derzeit festgelegten Zielplattformen angezeigt.

![Projekteigenschaften für Portable Class Library in Visual Studio](media/pcl-project-properties.png)

Wählen Sie zum Hinzufügen oder Entfernen von Zielen, die **Änderung** Schaltfläche und dann die entsprechenden Kontrollkästchen deaktivieren.

Wenn Sie die Zielplattformen ändern, passen sich auch die APIs, die Ihnen zum Entwickeln des Projekts zur Verfügung stehen, Ihrer Auswahl an. Visual Studio meldet die Fehler und Warnungen, die durch den Wechsel der Zielplattformen entstehen können.

Wenn Sie die Portabilität auswerten möchten Ihre Assemblys, bevor Sie Änderungen in Visual Studio vornehmen, können Sie verwenden die [.NET Portability Analyzer](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b).

## <a name="supported-types-and-members"></a>Unterstützte Typen und Members

Die Typen und Member, die in Projekten für portable Klassenbibliotheken verfügbar sind, werden von mehreren Kompatibilitätsfaktoren beschränkt:

-   Sie müssen von allen Zielen, die Sie ausgewählt haben, gemeinsam nutzbar sein.

-   Sie müssen sich auf diesen Zielen in ähnlicher Weise verhalten.

-   Sie dürfen keine Kandidaten für Veraltung sein.

-   Sie müssen jedoch in einer übertragbaren Umgebung einen Sinn ergeben, insbesondere wenn sie nicht übertragbare Member unterstützen.

Wird ein Member in der portablen Klassenbibliothek und für Ihre Ziele unterstützt, erscheint es in Ihrem Projekt in IntelliSense. Beachten Sie aber, dass eine API zwar in der portablen Klassenbibliothek unterstützt werden kann, ob Sie die API jedoch verwenden können, hängt von den gewählten Zielen ab.

## <a name="api-differences-in-the-portable-class-library"></a>API-Unterschiede in der portablen Klassenbibliothek

Um die Kompatibilität von Assemblys für portable Klassenbibliotheken mit allen unterstützten Plattformen sicherzustellen, wurden einige Member in der portablen Klassenbibliothek geringfügig geändert.

## <a name="use-the-portable-class-library"></a>Verwenden der portablen Klassenbibliothek

Nachdem Sie das Projekt für die portable Klassenbibliothek erstellt haben, verweisen Sie einfach aus anderen Projekten auf das neue Projekt. Sie können entweder auf das Projekt oder auf bestimmte Assemblys verweisen, die die Klassen enthalten, auf die Sie zugreifen möchten.

Um eine App auszuführen, die auf die Assembly einer portablen Klassenbibliothek verweist, müssen auf dem Computer die erforderlichen Versionen (oder höhere Versionen) der Zielplattformen installiert sein. Visual Studio enthält alle erforderlichen Frameworks, sodass Sie die App ohne weitere Änderung auf dem Computer ausführen können, auf dem Sie die Anwendung entwickelt haben.

### <a name="deploy-a-universal-windows-app"></a>Bereitstellen einer universellen Windows-app

Wenn Sie eine universelle Windows-app erstellen, die auf die Assembly einer portablen Klassenbibliothek verweist, ist alles, was Sie zum Bereitstellen der app benötigen im app-Paket enthalten und es sind keine weiteren Schritte erforderlich.

### <a name="deploy-a-net-framework-app"></a>Bereitstellen einer .NET Framework-app

Wenn Sie eine .NET Framework-App bereitstellen, die auf eine Assembly einer portablen Klassenbibliothek verweist, müssen Sie eine Abhängigkeit von der richtigen Version von .NET Framework angeben. Durch die Angabe dieser Abhängigkeit stellen Sie sicher, dass die erforderliche Version mit der App installiert wird.

-   Um eine Abhängigkeit mit ClickOnce-Bereitstellung zu erstellen: In **Projektmappen-Explorer**, wählen Sie den Projektknoten für das Projekt, das Sie veröffentlichen möchten. (Dies ist das Projekt, mit dem auf das Projekt der portablen Klassenbibliothek verwiesen wird.) Wählen Sie auf der Menüleiste **Projekt** > **Eigenschaften**, und wählen Sie dann die **veröffentlichen** Registerkarte. Auf der **veröffentlichen** Seite **Voraussetzungen**. Wählen Sie die erforderliche .NET Framework-Version als erforderliche Komponente aus.

-   Um eine Abhängigkeit mit einem Setup-Projekt zu erstellen: In **Projektmappen-Explorer**, wählen Sie das Setupprojekt. Wählen Sie auf der Menüleiste **Projekt** > **Eigenschaften** > **Voraussetzungen**. Wählen Sie die erforderliche .NET Framework-Version als erforderliche Komponente aus.

Weitere Informationen zum Bereitstellen von .NET Framework-apps finden Sie unter [Bereitstellungshandbuch für Entwickler](../../../docs/framework/deployment/deployment-guide-for-developers.md).

## <a name="see-also"></a>Siehe auch

- [Verwenden der portablen Klassenbibliothek mit MVVM](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md)
- [App-Ressourcen für Bibliotheken, die für mehrere Zielplattformen konfiguriert sind](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md)
- [.NET Portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
- [Bereitstellung](../../../docs/framework/deployment/net-framework-applications.md)
