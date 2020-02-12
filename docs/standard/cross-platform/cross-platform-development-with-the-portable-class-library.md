---
title: Plattformübergreifende Entwicklung mit der portablen Klassenbibliothek
ms.date: 09/17/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Portable Class Library [.NET Framework]
- targeting multiple platforms
- multiple platforms, targeting
ms.assetid: c31e1663-c164-4e65-b66d-d3aa8750a154
ms.openlocfilehash: dd5e5612de15a499c0dce34dc30faa6fd5731c17
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124532"
---
# <a name="cross-platform-development-with-the-portable-class-library"></a>Plattformübergreifende Entwicklung mit der portablen Klassenbibliothek

Mit dem Projekttyp der portablen Klassenbibliothek in Visual Studio können Sie plattformübergreifende apps und Bibliotheken für Microsoft-Plattformen schnell und einfach erstellen.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

Portable Klassenbibliotheken können den Zeit- und Kostenaufwand für die Entwicklung und das Testen von Code verringern. Verwenden Sie diesen Projekttyp zum Schreiben und Erstellen von portablen .NET Framework Assemblys, und verweisen Sie dann auf diese Assemblys von apps, die auf mehrere Plattformen abzielen, z. b. die .NET Framework

Auch nachdem Sie ein Projekt für eine portable Klassenbibliothek in Visual Studio erstellt haben und mit dem Entwickeln beginnen, können Sie die Zielplattformen noch ändern. Visual Studio kompiliert Ihre Bibliothek mit den neuen Assemblys, die Ihnen helfen, die Änderungen zu identifizieren, die Sie im Code vornehmen müssen.

## <a name="create-a-portable-class-library-project"></a>Erstellen eines Projekts für eine portable Klassenbibliothek

Verwenden Sie die in Visual Studio bereitgestellte Vorlage, um eine portable Klassenbibliothek zu erstellen. Erstellen Sie ein neues Projekt (**Datei** > **Neues Projekt**), und wählen Sie im Dialogfeld **Neues Projekt** Ihre Programmiersprache (Visual C# oder Visual Basic) aus. Wählen Sie dann die Vorlage **Klassenbibliothek (Legacy-portabel)** aus. Geben Sie einen Namen für das Projekt ein, und klicken Sie auf **OK**.

Das Dialogfeld **portable Klassenbibliothek hinzufügen** wird angezeigt. Wählen Sie zwei oder mehr Ziele aus, und **Klicken**Sie dann auf OK.

![Hinzufügen von Zielen der portablen Klassenbibliothek in Visual Studio](media/add-portable-class-library.png)

## <a name="change-targets"></a>Ziele ändern

Sie können die Zielplattformen eines Projekts für eine portable Klassenbibliothek ändern, wenn Sie es erstellen oder nachdem Sie die Entwicklung gestartet haben. Wenn Sie die Ziele nach dem Erstellen des Projekts ändern möchten, öffnen Sie in **Projektmappen-Explorer**das Kontextmenü für das Projekt für die portable Klassenbibliothek (nicht die Projekt Mappe), und wählen Sie dann **Eigenschaften**aus. Auf der Seite Projekteigenschaften werden auf der Registerkarte **Bibliothek** die Plattformen angezeigt, auf die das Projekt zurzeit abzielt.

![Projekteigenschaften für die portable Klassenbibliothek in Visual Studio](media/pcl-project-properties.png)

Um Ziele hinzuzufügen oder zu entfernen, wählen Sie die Schaltfläche **ändern** aus, und deaktivieren Sie dann die entsprechenden Kontrollkästchen.

Wenn Sie die Zielplattformen ändern, passen sich auch die APIs, die Ihnen zum Entwickeln des Projekts zur Verfügung stehen, Ihrer Auswahl an. Visual Studio meldet die Fehler und Warnungen, die durch den Wechsel der Zielplattformen entstehen können.

Wenn Sie die Portabilität Ihrer Assemblys auswerten möchten, bevor Sie Änderungen in Visual Studio vornehmen, können Sie die [.net-Portabilitäts Analyse](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)verwenden.

## <a name="supported-types-and-members"></a>Unterstützte Typen und Members

Die Typen und Member, die in Projekten für portable Klassenbibliotheken verfügbar sind, werden von mehreren Kompatibilitätsfaktoren beschränkt:

- Sie müssen von allen Zielen, die Sie ausgewählt haben, gemeinsam nutzbar sein.

- Sie müssen sich auf diesen Zielen in ähnlicher Weise verhalten.

- Sie dürfen keine Kandidaten für Veraltung sein.

- Sie müssen jedoch in einer übertragbaren Umgebung einen Sinn ergeben, insbesondere wenn sie nicht übertragbare Member unterstützen.

Wird ein Member in der portablen Klassenbibliothek und für Ihre Ziele unterstützt, erscheint es in Ihrem Projekt in IntelliSense. Beachten Sie aber, dass eine API zwar in der portablen Klassenbibliothek unterstützt werden kann, ob Sie die API jedoch verwenden können, hängt von den gewählten Zielen ab.

## <a name="api-differences-in-the-portable-class-library"></a>API-Unterschiede in der portablen Klassenbibliothek

Um die Kompatibilität von Assemblys für portable Klassenbibliotheken mit allen unterstützten Plattformen sicherzustellen, wurden einige Member in der portablen Klassenbibliothek geringfügig geändert.

## <a name="use-the-portable-class-library"></a>Verwenden der portablen Klassenbibliothek

Nachdem Sie das Projekt für die portable Klassenbibliothek erstellt haben, verweisen Sie einfach aus anderen Projekten auf das neue Projekt. Sie können entweder auf das Projekt oder auf bestimmte Assemblys verweisen, die die Klassen enthalten, auf die Sie zugreifen möchten.

Um eine App auszuführen, die auf die Assembly einer portablen Klassenbibliothek verweist, müssen auf dem Computer die erforderlichen Versionen (oder höhere Versionen) der Zielplattformen installiert sein. Visual Studio enthält alle erforderlichen Frameworks, sodass Sie die App ohne weitere Änderung auf dem Computer ausführen können, auf dem Sie die Anwendung entwickelt haben.

### <a name="deploy-a-universal-windows-app"></a>Bereitstellen einer universellen Windows-App

Wenn Sie eine universelle Windows-app erstellen, die auf eine Assembly einer portablen Klassenbibliothek verweist, ist alles, was Sie zum Bereitstellen der APP benötigen, im App-Paket enthalten, und es sind keine weiteren Schritte erforderlich.

### <a name="deploy-a-net-framework-app"></a>Bereitstellen einer .NET Framework-App

Wenn Sie eine .NET Framework-App bereitstellen, die auf eine Assembly einer portablen Klassenbibliothek verweist, müssen Sie eine Abhängigkeit von der richtigen Version von .NET Framework angeben. Durch die Angabe dieser Abhängigkeit stellen Sie sicher, dass die erforderliche Version mit der App installiert wird.

- So erstellen Sie eine Abhängigkeit mit der ClickOnce-Bereitstellung: Wählen Sie in **Projektmappen-Explorer**den Projekt Knoten für das Projekt aus, das Sie veröffentlichen möchten. (Dies ist das Projekt, das auf das Projekt der portablen Klassenbibliothek verweist.) Wählen Sie in der Menüleiste **Projekt** > **Eigenschaften**aus, und wählen Sie dann die Registerkarte **veröffentlichen** aus. Wählen Sie auf der Seite **veröffentlichen** die Option **Voraussetzungen**aus. Wählen Sie die erforderliche .NET Framework-Version als erforderliche Komponente aus.

- So erstellen Sie eine Abhängigkeit mit einem Setup-Projekt: Wählen Sie in **Projektmappen-Explorer**das Setup-Projekt aus. Wählen Sie in der Menüleiste **Projekt** > **Eigenschaften** > **Voraussetzungen**aus. Wählen Sie die erforderliche .NET Framework-Version als erforderliche Komponente aus.

Weitere Informationen zum Bereitstellen von .NET Framework-apps finden Sie im [Bereitstellungs Handbuch für Entwickler](../../../docs/framework/deployment/deployment-guide-for-developers.md).

## <a name="see-also"></a>Weitere Informationen

- [Verwenden der portablen Klassenbibliothek mit MVVM](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md)
- [App-Ressourcen für Bibliotheken, die für mehrere Zielplattformen konfiguriert sind](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md)
- [.NET Portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)
- [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
- [Bereitstellung](../../../docs/framework/deployment/net-framework-applications.md)
