---
title: "Vorgehensweise: Endpunkte im Unternehmen sperren | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1b7eaab7-da60-4cf7-9d6a-ec02709cf75d
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Vorgehensweise: Endpunkte im Unternehmen sperren
Von Großunternehmen wird oft gefordert, dass Anwendungen unter Einhaltung der Sicherheitsrichtlinien der Unternehmen entwickelt werden.  In diesem Thema wird behandelt, wie eine Clientendpunktbestätigung entwickelt und installiert wird, die zur Validierung aller auf Computern installierten [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Clientanwendungen verwendet werden kann.  
  
 In diesem Fall handelt es sich bei der Bestätigung um eine Clientbestätigung, da dieses Endpunktverhalten dem Clientabschnitt [\<commonBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) der Datei „machine.config“ hinzugefügt wird.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] lädt gemeinsames Endpunktverhalten nur für Clientanwendungen und gemeinsames Dienstverhalten nur für Dienstanwendungen.  Um diese Bestätigung für Dienstanwendungen installieren zu können, muss es sich bei der Bestätigung um ein Dienstverhalten handeln.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] Der Abschnitt [\<commonBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md).  
  
> [!IMPORTANT]
>  Dienst\- oder Endpunktverhaltensweisen, die nicht mit dem <xref:System.Security.AllowPartiallyTrustedCallersAttribute>\-Attribut \(APTCA\) markiert sind und die dem Abschnitt [\<commonBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) einer Konfigurationsdatei hinzugefügt wurden, werden nicht ausgeführt, wenn die Anwendung in einer teilweise vertrauenswürdigen Umgebung ausgeführt wird. In diesem Fall wird auch keine Ausnahme ausgelöst.  Um die Ausführung gemeinsamer Verhalten, wie z.&\#160;B. Bestätigungen, zu erzwingen, müssen Sie einen der beiden folgenden Schritte ausführen:  
>   
>  &\#8211; Markieren Sie das gemeinsame Verhalten mit dem <xref:System.Security.AllowPartiallyTrustedCallersAttribute>\-Attribut, damit es ausgeführt werden kann, wenn es als teilweise vertrauenswürdige Anwendung bereitgestellt wird.  Beachten Sie, dass auf dem Computer ein Registrierungseintrag festgelegt werden kann, um die Ausführung von mit APTCA markierten Assemblys zu verhindern.  
>   
>  &\#8211; Wenn die Anwendung als voll vertrauenswürdige Anwendung bereitgestellt wird, stellen Sie sicher, dass die Benutzer die Sicherheitseinstellungen für den Codezugriff nicht dahingehend ändern können, dass die Anwendung in einer teilweise vertrauenswürdigen Umgebung ausgeführt werden kann.  Wenn sie dies können, dann wird die benutzerdefinierte Bestätigung nicht ausgeführt, und es wird keine Ausnahme ausgelöst.  Eine Möglichkeit, dieses sicherzustellen, wird unter der `levelfinal`\-Option in [Sicherheitsrichtlinientool für den Codezugriff \(Caspol.exe\)](http://go.microsoft.com/fwlink/?LinkId=248222) beschrieben.  
>   
>  Weitere Informationen finden Sie unter [Empfehlungen für eine teilweise vertrauenswürdige Umgebung](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) und [Unterstützte Bereitstellungsszenarien](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md).  
  
### So erstellen Sie eine Endpunktbestätigung  
  
1.  Erstellen Sie ein <xref:System.ServiceModel.Description.IEndpointBehavior> mit den gewünschten Validierungsschritten in der <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A>\-Methode.  Der folgende Code veranschaulicht dies.  \(Das `InternetClientValidatorBehavior` stammt aus dem Beispiel [Sicherheitsvalidierung](../../../../docs/framework/wcf/samples/security-validation.md).\)  
  
     [!code-csharp[LockdownValidation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorbehavior.cs#2)]  
  
2.  Erstellen Sie ein neues <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, des die in Schritt 1 erstellte Endpunktbestätigung registriert.  Dies wird im folgenden Codebeispiel gezeigt.  \(Der ursprüngliche Code für dieses Beispiel befindet sich im Codebeispiel [Sicherheitsvalidierung](../../../../docs/framework/wcf/samples/security-validation.md).\)  
  
     [!code-csharp[LockdownValidation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorelement.cs#3)]  
  
3.  Stellen Sie sicher, dass die kompilierte Assembly mit einem starken Namen signiert wird.  Ausführliche Informationen finden Sie unter [Strong Name\-Tool \(SN.EXE\)](http://go.microsoft.com/fwlink/?LinkId=248217) und den Compilerbefehlen der verwendeten Sprache.  
  
### So installieren Sie die Bestätigung auf dem Zielcomputer  
  
1.  Installieren Sie die Endpunktbestätigung mithilfe des entsprechenden Mechanismus.  In einem Unternehmen kann dies die Verwendung der Gruppenrichtlinie und des Systems Management Server \(SMS\) sein.  
  
2.  Installieren Sie mithilfe von [Gacutil.exe \(Global Assembly Cache\-Tool\)](http://msdn.microsoft.com/library/ex0ss12c\(v=vs.110\).aspx) die Assembly mit starkem Namen im globalen Assemblycache.  
  
3.  Verwenden Sie die <xref:System.Configuration?displayProperty=fullName>\-Namespacetypen, um Folgendes durchzuführen:  
  
    1.  Fügen Sie die Erweiterung dem Abschnitt [\<behaviorExtensions\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md) unter Angabe eines vollqualifizierten Typnamens hinzu, und sperren Sie das Element.  
  
         [!code-csharp[LockdownValidation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#5)]  
  
    2.  Fügen Sie das Verhaltenselement der `EndpointBehaviors`\-Eigenschaft des [\<commonBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)\-Abschnitts hinzu, und sperren Sie das Element.  \(Um eine Bestätigung auf der Dienstseite zu installieren, muss die Bestätigung ein <xref:System.ServiceModel.Description.IServiceBehavior> sein und zur `ServiceBehaviors`\-Eigenschaft hinzugefügt werden.\) Das folgende Codebeispiel veranschaulicht die ordnungsgemäße Konfiguration nach den Schritten a.  und b. Der einzige Unterschied ist, dass hier kein starker Name vergeben wird.  
  
         [!code-csharp[LockdownValidation#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#6)]  
  
    3.  Speichern Sie die Datei machine.config.  Das folgende Codebeispiel führt alle Aufgaben in Schritt 3 durch, speichert aber eine lokale Kopie der geänderten Datei machine.config.  
  
         [!code-csharp[LockdownValidation#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#7)]  
  
## Beispiel  
 Das folgende Codebeispiel veranschaulicht, wie ein gemeinsames Verhalten zu einer machine.config\-Datei hinzugefügt und wie eine Kopie auf der Festplatte gespeichert wird.  Das `InternetClientValidatorBehavior` stammt aus dem Beispiel [Sicherheitsvalidierung](../../../../docs/framework/wcf/samples/security-validation.md).  
  
 [!code-csharp[LockdownValidation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#1)]  
  
## .NET Framework-Sicherheit  
 Sie können darüber hinaus die Elemente der Konfigurationsdatei verschlüsseln.  Weitere Informationen finden Sie im Abschnitt "Siehe auch".  
  
## Siehe auch  
 [Verschlüsseln von Konfigurationsdateielementen mit DPAPI](http://go.microsoft.com/fwlink/?LinkId=94954)   
 [Verschlüsseln von Konfigurationsdateielementen mit RSA](http://go.microsoft.com/fwlink/?LinkId=94955)