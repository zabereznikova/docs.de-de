---
title: 'Vorgehensweise: Endpunkte im Unternehmen sperren'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b7eaab7-da60-4cf7-9d6a-ec02709cf75d
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5b6fa36a269dec4a191417813ec9c4ee26b699ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-lock-down-endpoints-in-the-enterprise"></a>Vorgehensweise: Endpunkte im Unternehmen sperren
Von Großunternehmen wird oft gefordert, dass Anwendungen unter Einhaltung der Sicherheitsrichtlinien der Unternehmen entwickelt werden. In diesem Thema wird behandelt, wie eine Clientendpunktbestätigung entwickelt und installiert wird, die zur Validierung aller auf Computern installierten [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Clientanwendungen verwendet werden kann.  
  
 In diesem Fall wird das Validierungssteuerelement eine Clientbestätigung, da dieses Endpunktverhalten, an den Client hinzugefügt wird [ \<CommonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) Abschnitt in der Datei "Machine.config". [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] lädt gemeinsames Endpunktverhalten nur für Clientanwendungen und gemeinsames Dienstverhalten nur für Dienstanwendungen. Um diese Bestätigung für Dienstanwendungen installieren zu können, muss es sich bei der Bestätigung um ein Dienstverhalten handeln. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]die [ \<CommonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) Abschnitt.  
  
> [!IMPORTANT]
>  Dienst- oder Endpunktverhaltensweisen nicht gekennzeichnet werden, mit der <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut (APTCA), die hinzugefügt werden, die [ \<CommonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) Abschnitt einer Konfigurationsdatei werden nicht ausgeführt, wenn in einer teilweise vertrauenswürdigen Anwendung ausgeführt wird Umgebung und keine Ausnahme wird ausgelöst, wenn in diesem Fall. Um die Ausführung gemeinsamer Verhalten, wie z.&#160;B. Bestätigungen, zu erzwingen, müssen Sie einen der beiden folgenden Schritte ausführen:  
>   
>  &#8211; Markieren Sie das gemeinsame Verhalten mit dem <xref:System.Security.AllowPartiallyTrustedCallersAttribute>-Attribut, damit es ausgeführt werden kann, wenn es als teilweise vertrauenswürdige Anwendung bereitgestellt wird. Beachten Sie, dass auf dem Computer ein Registrierungseintrag festgelegt werden kann, um die Ausführung von mit APTCA markierten Assemblys zu verhindern.  
>   
>  &#8211; Wenn die Anwendung als voll vertrauenswürdige Anwendung bereitgestellt wird, stellen Sie sicher, dass die Benutzer die Sicherheitseinstellungen für den Codezugriff nicht dahingehend ändern können, dass die Anwendung in einer teilweise vertrauenswürdigen Umgebung ausgeführt werden kann. Wenn sie dies können, dann wird die benutzerdefinierte Bestätigung nicht ausgeführt, und es wird keine Ausnahme ausgelöst. Eine Möglichkeit, dies sicherzustellen, finden Sie unter der `levelfinal` -Option [Code Access Security Policy-Tool (Caspol.exe)](http://go.microsoft.com/fwlink/?LinkId=248222).  
>   
>  Weitere Informationen finden Sie unter [teilweise Vertrauenswürdigkeit bewährte](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) und [Unterstützte Bereitstellungsszenarien](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md).  
  
### <a name="to-create-the-endpoint-validator"></a>So erstellen Sie eine Endpunktbestätigung  
  
1.  Erstellen Sie ein <xref:System.ServiceModel.Description.IEndpointBehavior> mit den gewünschten Validierungsschritten in der <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A>-Methode. Der folgende Code veranschaulicht dies. (Die `InternetClientValidatorBehavior` stammt aus dem [Sicherheitsvalidierung](../../../../docs/framework/wcf/samples/security-validation.md) Beispiel.)  
  
     [!code-csharp[LockdownValidation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorbehavior.cs#2)]  
  
2.  Erstellen Sie ein neues <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, des die in Schritt 1 erstellte Endpunktbestätigung registriert. Dies wird im folgenden Codebeispiel gezeigt. (Der ursprüngliche Code für dieses Beispiel befindet sich in der [Sicherheitsvalidierung](../../../../docs/framework/wcf/samples/security-validation.md) Beispiel.)  
  
     [!code-csharp[LockdownValidation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorelement.cs#3)]  
  
3.  Stellen Sie sicher, dass die kompilierte Assembly mit einem starken Namen signiert wird. Weitere Informationen finden Sie unter der [Strong Name-Tool ("sn". EXE-Datei)](http://go.microsoft.com/fwlink/?LinkId=248217) und die Compilerbefehle für Ihre Sprache.  
  
### <a name="to-install-the-validator-into-the-target-computer"></a>So installieren Sie die Bestätigung auf dem Zielcomputer  
  
1.  Installieren Sie die Endpunktbestätigung mithilfe des entsprechenden Mechanismus. In einem Unternehmen kann dies die Verwendung der Gruppenrichtlinie und des Systems Management Server (SMS) sein.  
  
2.  Installieren Sie die Assembly mit starkem Namen in das global Assembly Cache mithilfe der [Gacutil.exe (Global Assembly Cache-Tool)](http://msdn.microsoft.com/library/ex0ss12c\(v=vs.110\).aspx).  
  
3.  Verwenden Sie die <xref:System.Configuration?displayProperty=nameWithType>-Namespacetypen, um Folgendes durchzuführen:  
  
    1.  Fügen Sie die Erweiterung der [ \<BehaviorExtensions >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md) Abschnitt eines vollqualifizierten Typnamens und Sperren Sie das Element.  
  
         [!code-csharp[LockdownValidation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#5)]  
  
    2.  Fügen Sie das verhaltenselement der `EndpointBehaviors` Eigenschaft von der [ \<CommonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) Textabschnitt und Sperren Sie das Element. (Um eine Bestätigung auf der Dienstseite zu installieren, muss die Bestätigung ein <xref:System.ServiceModel.Description.IServiceBehavior> sein und zur `ServiceBehaviors`-Eigenschaft hinzugefügt werden.) Das folgende Codebeispiel veranschaulicht die ordnungsgemäße Konfiguration nach den Schritten a. und b. Der einzige Unterschied ist, dass hier kein starker Name vergeben wird.  
  
         [!code-csharp[LockdownValidation#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#6)]  
  
    3.  Speichern Sie die Datei machine.config. Das folgende Codebeispiel führt alle Aufgaben in Schritt 3 durch, speichert aber eine lokale Kopie der geänderten Datei machine.config.  
  
         [!code-csharp[LockdownValidation#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#7)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht, wie ein gemeinsames Verhalten zu einer machine.config-Datei hinzugefügt und wie eine Kopie auf der Festplatte gespeichert wird. Die `InternetClientValidatorBehavior` stammt aus dem [Sicherheitsvalidierung](../../../../docs/framework/wcf/samples/security-validation.md) Beispiel.  
  
 [!code-csharp[LockdownValidation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#1)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Sie können darüber hinaus die Elemente der Konfigurationsdatei verschlüsseln. Weitere Informationen finden Sie im Abschnitt "Siehe auch".  
  
## <a name="see-also"></a>Siehe auch  
 [Verschlüsseln von konfigurationsdateielementen mit DPAPI](http://go.microsoft.com/fwlink/?LinkId=94954)  
 [Verschlüsseln von konfigurationsdateielementen mit RSA](http://go.microsoft.com/fwlink/?LinkId=94955)
