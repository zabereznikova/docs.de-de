---
title: Erweitern des My-Namespaces in Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.AddingMyExtensions
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
ms.openlocfilehash: 22d9d0def302b870de6f3e5ca4c142758b21314c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591832"
---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Erweitern des My-Namespaces in Visual Basic
Die `My` Namespaces in Visual Basic macht Eigenschaften und Methoden, mit denen Sie einfach die Leistungsfähigkeit von .NET Framework nutzen können. Die `My` Namespace vereinfacht allgemeine Programmierprobleme, löst häufig eine einzige Codezeile eine schwierige Aufgabe. Darüber hinaus die `My` Namespace ist vollständig erweiterbar, sodass Sie das Verhalten anpassen können `My` und fügen Sie neue Dienste in seine Hierarchie anwendungsspezifische Anforderungen angepasst werden kann. In diesem Artikel werden beide zum Anpassen von vorhandener Elementen von der `My` Namespace und wie Sie eigene benutzerdefinierte Klassen zum Hinzufügen der `My` Namespace.  
  
 **Themeninhalt**  
  
-   [Anpassen der vorhandene My Namespace-Elemente](#customizing)  
  
-   [Hinzufügen von Mitgliedern zu My-Objekte](#addingtoobjects)  
  
-   [Hinzufügen der benutzerdefinierten Objekte, die meine Namespace](#addingcustom)  
  
-   [Hinzufügen von Mitgliedern zu den My-Namespace](#addingtonamespace)  
  
-   [Hinzufügen von Ereignissen zu benutzerdefinierten My-Objekten](#addingevents)  
  
-   [Richtlinien für den Entwurf](#design)  
  
-   [Entwerfen von Klassenbibliotheken für meine](#designing)  
  
-   [Verpacken und Bereitstellen von Erweiterungen](#packaging)  
  
##  <a name="customizing"></a> Anpassen der vorhandene My Namespace-Elemente  
 Die `My` Namespace in Visual Basic macht häufig verwendete Informationen zu Ihrer Anwendung und Ihrem Computer. Eine vollständige Liste der Objekte in der `My` Namespace finden Sie unter [My Reference](../../../visual-basic/language-reference/keywords/my-reference.md). Möglicherweise müssen Sie die vorhandenen Mitglieder Anpassen der `My` Namespace, damit sie besser entsprechen die Anforderungen Ihrer Anwendung. Eine Eigenschaft eines Objekts in der `My` Namespace, der nicht schreibgeschützt ist, kann auf einen benutzerdefinierten Wert festgelegt werden.  
  
 Nehmen wir beispielsweise an, dass Sie häufig verwenden die `My.User` Objekt, das den aktuellen Sicherheitskontext für den Benutzer ein Ausführen Ihrer Anwendung zugreifen. Allerdings verwendet Ihr Unternehmen ein benutzerdefiniertes Objekt, um zusätzliche Informationen und Funktionen für Benutzer innerhalb des Unternehmens verfügbar zu machen. In diesem Szenario können Sie den Standardwert ersetzen die `My.User.CurrentPrincipal` Eigenschaft mit einer Instanz von Ihren eigenen benutzerdefinierten principal-Objekt, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbcnExtendingMy#1](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_1.vb)]  
  
 Festlegen der `CurrentPrincipal` Eigenschaft auf die `My.User` Objekt ändert die Identität, unter dem die Anwendung ausgeführt wird. Die `My.User` -Objekt wiederum gibt Informationen über den neu angegebenen Benutzer zurück.  
  
##  <a name="addingtoobjects"></a> Hinzufügen von Mitgliedern zu My-Objekte  
 Die Typen von zurückgegebenen `My.Application` und `My.Computer` sind definiert als `Partial` Klassen. Aus diesem Grund können Sie erweitern die `My.Application` und `My.Computer` Objekte durch das Erstellen einer `Partial` Klasse mit dem Namen `MyApplication` oder `MyComputer`. Die Klasse kann keiner `Private` Klasse. Bei Angabe von der Klasse als Teil der `My` -Namespace können Sie hinzufügen, Eigenschaften und Methoden, die mit werden die `My.Application` oder `My.Computer` Objekte.  
  
 Im folgenden Beispiel wird angenommen, eine Eigenschaft namens `DnsServerIPAddresses` auf die `My.Computer` Objekt.  
  
 [!code-vb[VbVbcnExtendingMy#2](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_2.vb)]  
  
##  <a name="addingcustom"></a> Hinzufügen der benutzerdefinierten Objekte, die meine Namespace  
 Obwohl die `My` Namespace bietet Lösungen für viele allgemeine Programmieraufgaben, treten ggf. die Aufgaben, die die `My` Namespace befasst sich nicht. Angenommen, Ihre Anwendung möglicherweise benutzerdefinierten Verzeichnisdienste für Benutzerdaten zugreifen oder Ihrer Anwendung können die Assemblys, die mit Visual Basic standardmäßig nicht installiert werden. Sie können erweitern die `My` Namespace, um benutzerdefinierte Lösungen für häufige Aufgaben enthalten, die für Ihre Umgebung spezifisch sind. Die `My` Namespace kann leicht erweitert werden, um neue Member, um den wachsenden Anforderungen zur Anwendung hinzufügen. Sie können darüber hinaus Bereitstellen Ihrer `My` Namespaceerweiterungen für andere Entwickler als Visual Basic-Vorlage.  
  
###  <a name="addingtonamespace"></a> Hinzufügen von Mitgliedern zu den My-Namespace  
 Da `My` ist ein Namespace wie allen anderen Namespaces können Sie Eigenschaften der obersten Ebene, hinzufügen, indem Sie einfach ein Modul hinzufügen und Angeben einer `Namespace` von `My`. Kommentieren Sie das Modul mit dem `HideModuleName` -Attribut wie im folgenden Beispiel gezeigt. Die `HideModuleName` Attribut wird sichergestellt, dass der Modulname von IntelliSense nicht, beim Anzeigen der Mitglieder angezeigt wird der `My` Namespace.  
  
 [!code-vb[VbVbcnExtendingMy#3](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_3.vb)]  
  
 Zum Hinzufügen von Mitgliedern zu den `My` Namespace, das Modul ggf. Eigenschaften hinzufügen. Für jede Eigenschaft hinzugefügt der `My` Namespace, fügen Sie ein privates Feld des Typs `ThreadSafeObjectProvider(Of T)`, wobei der Typ der von der benutzerdefinierten Eigenschaft zurückgegebene Typ ist. Dieses Feld wird verwendet, zum Erstellen von Instanzen der threadsicheres Objekt von der Eigenschaft zurückgegeben werden sollen, durch Aufrufen der `GetInstance` Methode. Daher empfängt jeden Thread, der die erweiterte Eigenschaft zugreift, eine eigene Instanz des zurückgegebenen Typs. Im folgenden Beispiel wird eine Eigenschaft namens `SampleExtension` vom Typ `SampleExtension` auf die `My` Namespace:  
  
 [!code-vb[VbVbcnExtendingMy#4](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_4.vb)]  
  
##  <a name="addingevents"></a> Hinzufügen von Ereignissen zu benutzerdefinierten My-Objekten  
 Können Sie die `My.Application` Objekt, das für Ihre benutzerdefinierten Ereignisse verfügbar machen `My` Objekte durch die Erweiterung der `MyApplication` partiellen Klasse in der `My` Namespace. Sie können für Windows-basierte Projekte Doppelklicken der **Mein Projekt** Knoten für das Projekt in **Projektmappen-Explorer**. In Visual Basic **Projekt-Designer**, klicken Sie auf die `Application` Registerkarte, und klicken Sie dann auf die `View Application Events` Schaltfläche. Eine neue Datei mit dem Namen ApplicationEvents.vb wird erstellt. Es enthält den folgenden Code zum Erweitern der `MyApplication` Klasse.  
  
 [!code-vb[VbVbcnExtendingMy#5](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_5.vb)]  
  
 Sie können Ereignishandler hinzufügen, für die benutzerdefinierte `My` Objekte durch Hinzufügen von benutzerdefinierten Ereignishandler, um die `MyApplication` Klasse. Benutzerdefinierte Ereignisse können Sie Code hinzufügen, der ausgeführt wird, wenn ein Ereignishandler hinzugefügt, entfernt, oder das Ereignis wird ausgelöst. Beachten Sie, dass die `AddHandler` code für ein benutzerdefiniertes Ereignis ausgeführt wird, nur, wenn Code von einem Benutzer für die Ereignisbehandlung hinzugefügt wird. Angenommen, Sie haben, die die `SampleExtension` Objekt aus dem vorherigen Abschnitt wurde eine `Load` Ereignis, das für einen benutzerdefinierten Ereignishandler hinzugefügt werden soll. Das folgende Codebeispiel zeigt einen benutzerdefinierten Ereignishandler namens `SampleExtensionLoad` , werden wird aufgerufen, wenn die `My.SampleExtension.Load` Ereignis auftritt. Wenn der Code zum Behandeln des neuen hinzugefügt wird `My.SampleExtensionLoad` Ereignis, das `AddHandler` Teil dieses Codes benutzerdefiniertes Ereignis ausgeführt wird. Die `MyApplication_SampleExtensionLoad` Methode ist im Codebeispiel wird ein Beispiel für einen Ereignishandler anzuzeigen, die verarbeitet enthalten die `My.SampleExtensionLoad` Ereignis. Beachten Sie, dass die `SampleExtensionLoad` Ereignis stehen bei der Auswahl der **Meine Anwendungsereignisse** -Option in der linken Dropdownliste oberhalb des Code-Editors beim Bearbeiten der Datei "ApplicationEvents.vb".  
  
 [!code-vb[VbVbcnExtendingMy#6](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_6.vb)]  
  
##  <a name="design"></a> Richtlinien für den Entwurf  
 Bei der Entwicklung von Erweiterungen für die `My` Namespace, verwenden Sie die folgenden Richtlinien, um die Wartungskosten für Ihrer Erweiterungskomponenten zu minimieren.  
  
-   **Schließen Sie nur die Erweiterungslogik.** Die Logik enthalten, die der `My` Erweiterung "Namespace" sollte nur den Code, der erforderlich ist, um die erforderliche Funktionalität in verfügbar zu machen enthalten die `My` Namespace. Da Ihre Erweiterung in Benutzerprojekten als Quellcode gespeichert werden soll, aktualisieren die Erweiterungskomponente fallen Wartungskosten hoher und sollte nach Möglichkeit vermieden werden.  
  
-   **Minimieren Sie Projektannahmen.** Ihre Erweiterungen der beim Erstellen der `My` Namespace, gehen Sie keinen Satz von Verweise, Importe auf Projektebene oder bestimmte compilereinstellungen (z. B. `Option Strict` deaktiviert). Stattdessen Abhängigkeiten zu minimieren und vollständig qualifizieren alle Typverweise mithilfe der `Global` Schlüsselwort. Stellen Sie außerdem sicher, dass die Erweiterung mit kompiliert `Option Strict` auf, um Fehler in der Erweiterung zu minimieren.  
  
-   **Isolieren Sie den Erweiterungscode ein.** Platzieren den Code in einer einzelnen Datei stellt die Erweiterung problemlos als Visual Studio-Elementvorlage bereitgestellt. Weitere Informationen finden Sie unter "Verpacken und Bereitstellen von Erweiterungen" weiter unten in diesem Thema. Platzieren alle der `My` Namespace Erweiterungscode in einer einzelnen Datei oder einen separaten Ordner in einem Projekt hilft Benutzern suchen auch die `My` Namespaceerweiterung.  
  
##  <a name="designing"></a> Entwerfen von Klassenbibliotheken für meine  
 Wie bei den meisten Objektmodelle der Fall ist, funktionieren einige Entwurfsmuster auch in der `My` -Namespace, andere dagegen nicht. Beim Entwerfen einer Erweiterung für die `My` Namespace, sollten Sie die folgenden Prinzipien:  
  
-   **Zustandslose Methoden.** Methoden in der `My` Namespace sollten eine vollständige Lösung für eine bestimmte Aufgabe bereitstellen. Stellen Sie sicher, dass die Parameterwerte, die an die Methode übergeben werden alle erforderlich, um die Aufgabe abzuschließen Input bereitstellen. Vermeiden Sie das Erstellen von Methoden, die auf früheren Zustand, wie die offene Verbindung mit Ressourcen abhängig sind.  
  
-   **Globale Instanzen.** Der einzige Zustand, der beibehalten wird die `My` Namespace ist global für das Projekt. Beispielsweise `My.Application.Info` kapselt Zustand, der in der gesamten Anwendung gemeinsam verwendet wird.  
  
-   **Einfache Parametertypen.** Halten Sie Dinge einfach durch das Vermeiden der komplexen Parametertypen. Erstellen Sie stattdessen die Methoden, die entweder keine Parametereingaben erfordern, oder, die anhand von einfache Eingabe Typen wie Zeichenfolgen, primitive Typen und So weiter.  
  
-   **Factorymethoden.** Einige Typen sind unbedingt schwierig zu instanziieren. Bereitstellen von Factorymethoden als Erweiterungen der `My` Namespace können Sie leichter ermitteln und Nutzen von Typen, die in diese Kategorie fallen. Ist ein Beispiel für eine Factorymethode, die gut funktioniert `My.Computer.FileSystem.OpenTextFileReader`. Es gibt mehrere Streamtypen in .NET Framework verfügbar. Durch Angabe von Textdateien insbesondere die `OpenTextFileReader` hilft dem Benutzer verstehen, welcher Stream zu verwenden.  
  
 Diese Richtlinien sind Allgemeine Entwurfsprinzipien für Klassenbibliotheken nicht ausgeschlossen. Vielmehr handelt es sich Empfehlungen, die für Entwickler optimiert werden, die Verwendung von Visual Basic und die `My` Namespace. Allgemeine Entwurfsprinzipien zum Erstellen von Klassenbibliotheken, finden Sie unter [Framework-Entwurfsrichtlinien](../../../standard/design-guidelines/index.md).  
  
##  <a name="packaging"></a> Verpacken und Bereitstellen von Erweiterungen  
 Sie können einschließen `My` Namespaceerweiterungen in einer Visual Studio-Projektvorlage, oder Sie können Ihre Erweiterung verpacken und bereitstellen wie ein Visual Studio-Elementvorlage. Wenn Sie Verpacken Ihrer `My` Namespaceerweiterungen als Visual Studio-Elementvorlage, profitieren Sie von zusätzlichen Funktionen von Visual Basic. Diese Funktionen ermöglichen es Ihnen, eine Erweiterung angeben, wenn ein Projekt auf eine bestimmte Assembly verweist, oder Aktivieren der Benutzer explizit hinzufügen Ihrer `My` Namespaceerweiterung mit der **My-Erweiterungen** Seite der Visual Basic Projekt-Designer.  
  
 Weitere Informationen über das Bereitstellen von `My` Namespaceerweiterungen finden Sie unter [Verpacken und Bereitstellen von benutzerdefinierten My Erweiterungen](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Packen und Bereitstellen von benutzerdefinierten My-Erweiterungen](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)  
 [Erweitern des Visual Basic-Anwendungsmodells](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)  
 [Anpassen der verfügbaren Objekte in „My“](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 [My-Erweiterungen-Seite, Projekt-Designer](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)  
 [Seite „Anwendung“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [Partial](../../../visual-basic/language-reference/modifiers/partial.md)
