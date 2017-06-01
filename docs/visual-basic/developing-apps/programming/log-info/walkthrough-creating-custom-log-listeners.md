---
title: Erstellen von benutzerdefinierten Protokolllistenern (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- custom log listeners
- My.Application.Log object, custom log listeners
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
caps.latest.revision: 19
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c7dd6ed1875abd37e72baf97950d21a110c5a6a8
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# <a name="walkthrough-creating-custom-log-listeners-visual-basic"></a>Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Protokolllistenern (Visual Basic)
Diese exemplarische Vorgehensweise veranschaulicht, wie Sie einen benutzerdefinierten Protokolllistener erstellen und ihn so konfigurieren, dass er der Ausgabe des `My.Application.Log`-Objekts lauscht.  
  
## <a name="getting-started"></a>Erste Schritte  
 Protokolllistener müssen von der <xref:System.Diagnostics.TraceListener>-Klasse erben.  
  
#### <a name="to-create-the-listener"></a>So erstellen Sie den Listener  
  
-   Erstellen Sie in Ihrer Anwendung eine Klasse mit dem Namen `SimpleListener`, die von <xref:System.Diagnostics.TraceListener> erbt.  
  
     [!code-vb[VbVbalrMyApplicationLog#16](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_1.vb)]  
  
     Die Methoden <xref:System.Diagnostics.TraceListener.Write%2A> und <xref:System.Diagnostics.TraceListener.WriteLine%2A> sind für die Basisklasse erforderlich und rufen `MsgBox` auf, um ihre Eingabe anzuzeigen.  
  
     Das <xref:System.Security.Permissions.HostProtectionAttribute>-Attribut wird auf die Methoden <xref:System.Diagnostics.TraceListener.Write%2A> und <xref:System.Diagnostics.TraceListener.WriteLine%2A> angewendet, damit ihre Attribute den Methoden der Basisklasse entsprechen. Mithilfe des Attributs <xref:System.Security.Permissions.HostProtectionAttribute> kann der Host, der den Code ausführt, ermitteln, ob der Code die Synchronisierung der Hostsicherheit verfügbar macht.  
  
    > [!NOTE]
    >  Das Attribut <xref:System.Security.Permissions.HostProtectionAttribute> ist nur in nicht verwalteten Anwendungen effektiv, die die Common Language Runtime hosten und Hostschutz implementieren, z.B. SQL Server.  
  
 Sie sollten der Assembly, die Ihren Protokolllistener enthält, einen starken Namen geben, um sicherzustellen, dass `My.Application.Log` Ihren Protokolllistener verwendet.  
  
 Im nächste Verfahren finden Sie einige einfache Schritte zum Erstellen einer Assembly mit starkem Namen und Protokolllistener. Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](https://msdn.microsoft.com/library/xwb8f617).  
  
#### <a name="to-strongly-name-the-log-listener-assembly"></a>So geben Sie der Assembly mit Protokolllistener einen starken Namen  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die Registerkarte **Signierung**.  
  
3.  Wählen Sie das Feld **Sign the assembly** (Assembly signieren) aus.  
  
4.  Wählen Sie in der Dropdownliste **Schlüsseldatei mit starkem Namen auswählen** **\<Neu>** aus.  
  
     Das Dialogfeld **Schlüssel für einen starken Namen erstellen** wird geöffnet.  
  
5.  Geben Sie einen Namen für die Schlüsseldatei im Feld **Schlüsseldateiname** ein.  
  
6.  Geben Sie in die Felder **Kennwort eingeben** und **Kennwort bestätigen** ein Kennwort ein.  
  
7.  Klicken Sie auf **OK**.  
  
8.  Erstellen Sie die Anwendung neu.  
  
## <a name="adding-the-listener"></a>Hinzufügen des Listeners  
 Da die Assembly jetzt über einen starken Namen verfügt, müssen Sie den starken Namen des Listeners bestimmen, damit `My.Application.Log` Ihren Protokolllistener verwendet.  
  
 Das Format für einen Typ mit starkem Namen ist wie folgt.  
  
 \<Typname>, \<Assemblyname>, \<Versionsnummer>, \<Kultur>, \<starker Name>  
  
#### <a name="to-determine-the-strong-name-of-the-listener"></a>So bestimmen Sie den starken Namen des Listeners  
  
-   Im folgenden Code wird gezeigt, wie Sie den Namen für den Typ mit starkem Namen für `SimpleListener` bestimmen.  
  
     [!code-vb[VbVbalrMyApplicationLog#17](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-creating-custom-log-listeners_2.vb)]  
  
     Der starke Name des Typs hängt von Ihrem Projekt ab.  
  
 Sie können mit dem starken Namen den Listener zur `My.Application.Log`-Auflistung der Protokolllistener hinzufügen.  
  
#### <a name="to-add-the-listener-to-myapplicationlog"></a>So fügen Sie den Listener zu „My.Application.Log“ hinzu  
  
1.  Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf „app.config“, und wählen Sie **Öffnen** aus.  
  
     - oder -   
  
     Wenn eine app.config-Datei vorhanden ist:  
  
    1.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
    2.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** den Eintrag **Anwendungskonfigurationsdatei**aus.  
  
    3.  Klicken Sie auf **Hinzufügen**.  
  
2.  Suchen Sie den `<listeners>` -Abschnitt, der sich im `<source>` -Abschnitt mit dem `name` -Attribut "DefaultSource" im Abschnitt `<sources>` befindet. Der Abschnitt `<sources>` befindet sich im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.  
  
3.  Fügen Sie dem Abschnitt `<listeners>` dieses Element hinzu:  
  
    ```  
    <add name="SimpleLog" />  
    ```  
  
4.  Suchen Sie den Abschnitt `<sharedListeners>` im `<system.diagnostics>` -Abschnitt im Abschnitt `<configuration>` der obersten Ebene.  
  
5.  Fügen Sie dem `<sharedListeners>` -Abschnitt dieses Element hinzu:  
  
    ```  
    <add name="SimpleLog" type="SimpleLogStrongName" />  
    ```  
  
     Ändern Sie den Wert von `SimpleLogStrongName` in den starken Namen des Listeners.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [Arbeiten mit Anwendungsprotokollen](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Vorgehensweise: Protokollieren von Ausnahmen](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)   
 [Vorgehensweise: Schreiben von Protokollmeldungen](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Exemplarische Vorgehensweise: Ändern des Orts, in den „My.Application.Log“ Informationen schreibt](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
