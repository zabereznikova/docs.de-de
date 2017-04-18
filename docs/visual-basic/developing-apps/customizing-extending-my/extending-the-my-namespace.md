---
title: Erweitern der meine Namespace in Visual Basic | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddingMyExtensions
dev_langs:
- VB
helpviewer_keywords:
- My namespace, customizing
- My namespace
- My namespace, extending
ms.assetid: 808e8617-b01c-4135-8b21-babe87389e8e
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1d1e957536f35b81a9672994c9d4d261afb764ea
ms.lasthandoff: 03/13/2017

---
# <a name="extending-the-my-namespace-in-visual-basic"></a>Erweitern des My-Namespaces in Visual Basic
Die `My` -Namespaces in Visual Basic macht Eigenschaften und Methoden, mit denen Sie problemlos die Leistungsfähigkeit von .NET Framework nutzen können. Der `My` -Namespace vereinfacht häufig auftretende Programmierprobleme, löst häufig eine schwierige Aufgabe zu einer einzelnen Zeile des Codes. Darüber hinaus die `My` Namespace ist vollständig erweiterbar, sodass Sie das Verhalten anpassen können `My` und seiner Hierarchie Anpassung an die spezifischen Anforderungen Ihrer Anwendung neue Dienste hinzuzufügen. Dieses Thema erläutert sowohl vorhandene Mitglieder Anpassen der `My` Namespace und zum Hinzufügen Ihrer eigenen benutzerdefinierten Klassen, die die `My` Namespace.  
  
 **Themeninhalt**  
  
-   [Anpassen von vorhandenen Meine Namespace-Elemente](#customizing)  
  
-   [Hinzufügen von Mitgliedern zu My-Objekten](#addingtoobjects)  
  
-   [Hinzufügen von benutzerdefinierten Objekten, die meine Namespace](#addingcustom)  
  
-   [Hinzufügen von Mitgliedern zu den Meine Namespace](#addingtonamespace)  
  
-   [Hinzufügen von Ereignissen zu benutzerdefinierten My-Objekten](#addingevents)  
  
-   [Entwurfsrichtlinien](#design)  
  
-   [Entwerfen von Klassenbibliotheken für meine](#designing)  
  
-   [Verpacken und Bereitstellen von Erweiterungen](#packaging)  
  
##  <a name="customizing"></a>Anpassen von vorhandenen Meine Namespace-Elemente  
 Der `My` -Namespace in Visual Basic macht häufig verwendete Informationen über die Anwendung und Ihrem Computer. Eine vollständige Liste der Objekte in der `My` -Namespace finden Sie unter [My Reference](../../../visual-basic/language-reference/keywords/my-reference.md). Möglicherweise müssen Sie die vorhandenen Mitglieder Anpassen der `My` Namespace, damit sie besser entsprechen die Anforderungen der Anwendung. Eine Eigenschaft eines Objekts in der `My` -Namespace, der nicht schreibgeschützt ist, kann auf einen benutzerdefinierten Wert festgelegt werden.  
  
 Nehmen wir beispielsweise an, Sie häufig verwenden das `My.User` -Objekt, das Zugriff auf den aktuellen Sicherheitskontext für den Benutzer die Anwendung ausführen. Ihr Unternehmen verwendet jedoch ein benutzerdefiniertes Objekt, um zusätzliche Informationen und Funktionen für Benutzer innerhalb des Unternehmens verfügbar zu machen. In diesem Szenario können Sie den Standardwert ersetzen die `My.User.CurrentPrincipal` Eigenschaft mit einer Instanz Ihres eigenen benutzerdefinierten Prinzipalobjekts, wie im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbVbcnExtendingMy&#1;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_1.vb)]  
  
 Festlegen der `CurrentPrincipal` Eigenschaft auf den `My.User` Objekt ändert sich die Identität, unter dem die Anwendung ausgeführt wird. Das `My.User` -Objekt wiederum gibt Informationen über den neu angegebenen Benutzer zurück.  
  
##  <a name="addingtoobjects"></a>Hinzufügen von Mitgliedern zu My-Objekten  
 Welche Typen von `My.Application` und `My.Computer` sind definiert als `Partial` Klassen. Daher können Sie erweitern die `My.Application` und `My.Computer` Objekte durch das Erstellen einer `Partial` Klasse mit dem Namen `MyApplication` oder `MyComputer`. Die Klasse kann keiner `Private` Klasse. Wenn Sie die Klasse als Teil des angeben der `My` -Namespace können Sie Eigenschaften und Methoden, die mit einbezogen Hinzufügen der `My.Application` oder `My.Computer` Objekte.  
  
 Im folgenden Beispiel wird z. B. eine Eigenschaft mit dem Namen `DnsServerIPAddresses` an die `My.Computer` Objekt.  
  
 [!code-vb[VbVbcnExtendingMy&#2;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_2.vb)]  
  
##  <a name="addingcustom"></a>Hinzufügen von benutzerdefinierten Objekten, die meine Namespace  
 Obwohl die `My` Namespace bietet Lösungen für viele allgemeine Programmieraufgaben, treten möglicherweise die Aufgaben, die `My` Namespace wird nicht behandelt. Z. B. kann benutzerdefinierte Verzeichnisdienste für Benutzerdaten auf die Anwendung zugreifen kann, oder Ihre Anwendung Assemblys, die mit Visual Basic standardmäßig nicht installiert werden. Sie können erweitern die `My` Namespace, um benutzerdefinierte Lösungen für häufige Aufgaben enthalten, die für Ihre Umgebung spezifisch sind. Die `My` Namespace kann problemlos erweitert werden, um neue Member, um die wachsenden Bedürfnisse zur Anwendung hinzufügen. Sie können darüber hinaus Bereitstellen Ihrer `My` Namespaceerweiterungen anderen Entwicklern als Visual Basic-Vorlage.  
  
###  <a name="addingtonamespace"></a>Hinzufügen von Mitgliedern zu den Meine Namespace  
 Da `My` ist ein Namespace Namespace, können Sie Eigenschaften der obersten Ebene, hinzufügen, indem Sie ein Modul hinzufügen und Angeben einer `Namespace` von `My`. Kommentieren Sie das Modul mit dem `HideModuleName` -Attribut wie im folgenden Beispiel gezeigt. Die `HideModuleName` -Attribut stellt sicher, dass der Modulname von IntelliSense nicht, beim Anzeigen der Mitglieder angezeigt wird der `My` Namespace.  
  
 [!code-vb[VbVbcnExtendingMy&3;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_3.vb)]  
  
 Zum Hinzufügen von Mitgliedern zu den `My` -Namespace hinzuzufügen, Eigenschaften für das Modul. Für jede Eigenschaft hinzugefügt, die `My` Namespace, fügen Sie ein privates Feld vom Typ `ThreadSafeObjectProvider(Of T)`, wobei der Typ der von der benutzerdefinierten Eigenschaft zurückgegebene Typ ist. Dieses Feld wird verwendet, um erstellen threadsicher Objektinstanzen, die von der Eigenschaft zurückgegeben werden, durch Aufrufen der `GetInstance` Methode. Daher empfängt jeder Thread, der die erweiterte Eigenschaft zugreift, eine eigene Instanz des zurückgegebenen Typs. Das folgende Beispiel fügt eine Eigenschaft namens `SampleExtension` vom Typ `SampleExtension` an die `My` Namespace:  
  
 [!code-vb[VbVbcnExtendingMy&4;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_4.vb)]  
  
##  <a name="addingevents"></a>Hinzufügen von Ereignissen zu benutzerdefinierten My-Objekten  
 Können Sie die `My.Application` -Objekt, das Ereignisse für Ihre benutzerdefinierten verfügbar zu machen `My` Objekte durch das Erweitern der `MyApplication` partielle Klasse in der `My` Namespace. Bei Windows-basierten Projekten können Sie doppelklicken die **Mein Projekt** Knoten für das Projekt im **Projektmappen-Explorer**. In der Visual Basic **Projekt-Designer**, klicken Sie auf die `Application` Registerkarte, und klicken Sie dann auf die `View Application Events` Schaltfläche. Eine neue Datei mit dem Namen ApplicationEvents.vb wird erstellt. Es enthält den folgenden Code zum Erweitern der `MyApplication` Klasse.  
  
 [!code-vb[VbVbcnExtendingMy&5;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_5.vb)]  
  
 Sie können Ereignishandler für Ihre benutzerdefinierten hinzufügen `My` Objekte durch Hinzufügen von benutzerdefinierten Ereignishandler der `MyApplication` Klasse. Benutzerdefinierte Ereignisse können Sie Code hinzufügen, der ausgeführt wird, wenn ein Ereignishandler hinzugefügt, entfernt, oder das Ereignis ausgelöst. Beachten Sie, dass die `AddHandler` code für ein benutzerdefiniertes Ereignis, das ausgeführt wird, nur, wenn Code von einem Benutzer für die Ereignisbehandlung hinzugefügt wird. Betrachten Sie z. B., die die `SampleExtension` Objekt aus dem vorherigen Abschnitt verfügt über ein `Load` -Ereignis, das Sie für einen benutzerdefinierten Ereignishandler hinzufügen möchten. Das folgende Codebeispiel zeigt einen benutzerdefinierten Ereignishandler mit dem Namen `SampleExtensionLoad` , werden aufgerufen wird, wenn die `My.SampleExtension.Load` Ereignis auftritt. Wenn der Code zum Behandeln des neuen hinzugefügt wird `My.SampleExtensionLoad` -Ereignis, das `AddHandler` Teil dieses benutzerdefinierten Ereigniscodes ausgeführt wird. Die `MyApplication_SampleExtensionLoad` Methode gehört das Codebeispiel, um ein Beispiel für einen Ereignishandler zu zeigen, behandelt der `My.SampleExtensionLoad` Ereignis. Beachten Sie, dass die `SampleExtensionLoad` Ereignis stehen bei der Auswahl der **My Application Events** -Option in der linken Dropdownliste oberhalb des Code-Editors beim Bearbeiten der Datei ApplicationEvents.vb.  
  
 [!code-vb[VbVbcnExtendingMy&6;](../../../visual-basic/developing-apps/customizing-extending-my/codesnippet/VisualBasic/extending-the-my-namespace_6.vb)]  
  
##  <a name="design"></a>Entwurfsrichtlinien  
 Bei der Entwicklung von Erweiterungen für den `My` -Namespace, verwenden Sie die folgenden Richtlinien, um die Wartungskosten Ihrer Erweiterung Komponenten zu minimieren.  
  
-   **Nur die Erweiterungslogik enthalten sein.** Die Logik enthalten, die der `My` Namespaceerweiterung sollte nur den Code, der erforderlich ist, um die erforderlichen Funktionen im verfügbar zu machen umfassen die `My` Namespace. Da Ihre Erweiterung in Benutzer Projekte als Quellcode befindet, Aktualisierung der Erweiterungskomponente verursacht eine hohe Wartungskosten und sollte möglichst vermieden werden.  
  
-   **Minimieren Sie Projektannahmen.** Beim Erstellen Ihrer Erweiterung der `My` -Namespace, gehen Sie nicht mehrere Verweise, Importe auf Projektebene oder bestimmten Compiler-Einstellungen (z. B. `Option Strict` deaktiviert). Stattdessen Abhängigkeiten zu minimieren und vollständig qualifizieren von allen Typverweisen mithilfe der `Global` Schlüsselwort. Stellen Sie außerdem sicher, dass die Erweiterung mit kompiliert `Option Strict` auf, um Fehler in der Erweiterung zu minimieren.  
  
-   **Isolieren Sie den Erweiterungscode.** Platzieren den Code in einer einzelnen Datei, kann Ihre Erweiterung problemlos als Visual Studio-Elementvorlage bereitgestellt werden. Weitere Informationen finden Sie unter "Verpacken und Bereitstellen von Erweiterungen" weiter unten in diesem Thema. Platzieren alle der `My` Namespace Erweiterungscode in einer einzelnen Datei oder einen separaten Ordner in einem Projekt können Benutzer finden das `My` Namespaceerweiterung.  
  
##  <a name="designing"></a>Entwerfen von Klassenbibliotheken für meine  
 Wie bei den meisten Objektmodellen funktionieren einige Entwurfsmuster gut in die `My` -Namespace, andere dagegen nicht. Beim Entwerfen einer Erweiterung für die `My` -Namespace, sollten Sie die folgenden Prinzipien:  
  
-   **Zustandslose Methoden.** Methoden in der `My` Namespace sollten eine vollständige Lösung für eine bestimmte Aufgabe bereitstellen. Stellen Sie sicher, dass die Parameterwerte, die an die Methode übergeben werden alle Eingaben erforderlich, um die jeweilige Aufgabe bereitstellen. Erstellung von Methoden, die auf den vorherigen Zustand, wie z. B. eine offene Verbindung zu Ressourcen zu vermeiden.  
  
-   **Globale Instanzen.** Der einzige Zustand, der beibehalten wird der `My` -Namespace ist global für das Projekt. Z. B. `My.Application.Info` kapselt Zustand, in der gesamten Anwendung verwendet wird.  
  
-   **Einfache Parametertypen.** Halten Sie Dinge einfach, indem Sie keine komplexen Parametertypen. Erstellen Sie stattdessen Methoden, die entweder keine Parametereingaben erfordern oder, die einfache Eingabetypen wie Zeichenfolgen, primitive Typen und So weiter nutzen.  
  
-   **Factory-Methoden.** Einige Typen sind unbedingt schwierig zu instanziieren. Bereitstellen von Factorymethoden als Erweiterungen der `My` -Namespace ermöglicht es Ihnen leichter ermitteln und Nutzung von Typen, die in diese Kategorie fallen. Ein Beispiel für eine Factorymethode, die gut funktioniert ist `My.Computer.FileSystem.OpenTextFileReader`. Es gibt mehrere Streamtypen in .NET Framework verfügbar. Insbesondere Textdateien angeben der `OpenTextFileReader` hilft dem Benutzer verstehen, welcher Stream verwendet.  
  
 Diese Richtlinien werden Allgemeine Entwurfsprinzipien für Klassenbibliotheken nicht entgegen. Vielmehr handelt es sich Empfehlungen, die für Entwickler optimiert sind, die Visual Basic verwenden und die `My` Namespace. Allgemeine Entwurfsprinzipien zum Erstellen von Klassenbibliotheken, finden Sie unter [Framework-Entwurfsrichtlinien](http://msdn.microsoft.com/library/5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b).  
  
##  <a name="packaging"></a>Verpacken und Bereitstellen von Erweiterungen  
 Sie können einschließen `My` Namespaceerweiterungen in einer Visual Studio-Projektvorlage, oder Sie können Ihre Erweiterungen Verpacken und Bereitstellen als Visual Studio-Elementvorlage. Wenn Sie Verpacken Ihrer `My` Namespaceerweiterungen als Visual Studio-Elementvorlage, profitieren Sie von zusätzlichen Funktionen von Visual Basic. Diese Funktionen ermöglichen es Ihnen, eine Erweiterung angeben, wenn ein Projekt auf eine bestimmte Assembly verweist, oder mit denen Benutzer explizit hinzufügen Ihrer `My` Namespaceerweiterung mithilfe der **My-Erweiterungen** im Visual Basic-Projekt-Designer auf der Seite.  
  
 Weitere Informationen zum Bereitstellen von `My` -Namespaceerweiterungen finden Sie unter [Verpacken und Bereitstellen von benutzerdefinierten My Erweiterungen](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verpacken und Bereitstellen von benutzerdefinierten My-Erweiterungen](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)   
 [Erweitern des Visual Basic-Anwendungsmodells](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)   
 [Anpassen der-Objekte sind verfügbar für meine](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [Meine Erweiterungen-Seite, Projekt-Designer](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)   
 [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)   
 [Partial](../../../visual-basic/language-reference/modifiers/partial.md)
