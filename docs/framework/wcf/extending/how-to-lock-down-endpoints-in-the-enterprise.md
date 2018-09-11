---
title: 'Vorgehensweise: Endpunkte im Unternehmen sperren'
ms.date: 03/30/2017
ms.assetid: 1b7eaab7-da60-4cf7-9d6a-ec02709cf75d
ms.openlocfilehash: 032b69c1fae38576b0374b329f1ab6fe90e2b1a0
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275261"
---
# <a name="how-to-lock-down-endpoints-in-the-enterprise"></a>Vorgehensweise: Endpunkte im Unternehmen sperren
Von Großunternehmen wird oft gefordert, dass Anwendungen unter Einhaltung der Sicherheitsrichtlinien der Unternehmen entwickelt werden. Im folgende Thema wird erläutert, wie zum Entwickeln und installieren eine clientendpunktbestätigung, die verwendet werden kann, überprüfen Sie alle Windows Communication Foundation (WCF)-Client-Anwendungen, die auf Computern installiert werden.  
  
 In diesem Fall wird das Validierungssteuerelement eine Clientbestätigung, da dieses Endpunktverhalten, an den Client hinzugefügt wird [ \<CommonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) Abschnitt in der Datei "Machine.config". WCF lädt gemeinsame Endpunktverhalten nur für Clientanwendungen und gemeinsames Dienstverhalten nur für dienstanwendungen. Um diese Bestätigung für Dienstanwendungen installieren zu können, muss es sich bei der Bestätigung um ein Dienstverhalten handeln. Weitere Informationen finden Sie unter den [ \<CommonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) Abschnitt.  
  
> [!IMPORTANT]
>  Dienst- oder Endpunktverhaltensweisen, die nicht mit dem gekennzeichnet werden die <xref:System.Security.AllowPartiallyTrustedCallersAttribute> -Attribut (APTCA), die hinzugefügt werden, die [ \<CommonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) Abschnitt einer Konfigurationsdatei werden nicht ausgeführt werden, wenn die Anwendung in einer teilweise vertrauenswürdigen ausgeführt wird Umgebung und keine Ausnahme wird ausgelöst, wenn dies der Fall. Um die Ausführung gemeinsamer Verhalten, wie z.&#160;B. Bestätigungen, zu erzwingen, müssen Sie einen der beiden folgenden Schritte ausführen:  
>   
>  &#8211; Markieren Sie das gemeinsame Verhalten mit dem <xref:System.Security.AllowPartiallyTrustedCallersAttribute>-Attribut, damit es ausgeführt werden kann, wenn es als teilweise vertrauenswürdige Anwendung bereitgestellt wird. Beachten Sie, dass auf dem Computer ein Registrierungseintrag festgelegt werden kann, um die Ausführung von mit APTCA markierten Assemblys zu verhindern.  
>   
>  &#8211; Wenn die Anwendung als voll vertrauenswürdige Anwendung bereitgestellt wird, stellen Sie sicher, dass die Benutzer die Sicherheitseinstellungen für den Codezugriff nicht dahingehend ändern können, dass die Anwendung in einer teilweise vertrauenswürdigen Umgebung ausgeführt werden kann. Wenn sie dies können, dann wird die benutzerdefinierte Bestätigung nicht ausgeführt, und es wird keine Ausnahme ausgelöst. Eine Möglichkeit, dies sicherzustellen, finden Sie unter den `levelfinal` -Option [Code Access Security Policy-Tool (Caspol.exe)](https://go.microsoft.com/fwlink/?LinkId=248222).  
>   
>  Weitere Informationen finden Sie unter [Partial Trust Best Practices](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) und [Supported Deployment Scenarios](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md).  
  
### <a name="to-create-the-endpoint-validator"></a>So erstellen Sie eine Endpunktbestätigung  
  
1.  Erstellen Sie ein <xref:System.ServiceModel.Description.IEndpointBehavior> mit den gewünschten Validierungsschritten in der <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A>-Methode. Der folgende Code veranschaulicht dies. (Die `InternetClientValidatorBehavior` stammt aus dem [Sicherheitsvalidierung](../../../../docs/framework/wcf/samples/security-validation.md) Beispiel.)  
  
     [!code-csharp[LockdownValidation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorbehavior.cs#2)]  
  
2.  Erstellen Sie ein neues <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, des die in Schritt 1 erstellte Endpunktbestätigung registriert. Dies wird im folgenden Codebeispiel gezeigt. (Der ursprüngliche Code für dieses Beispiel befindet sich in der [Sicherheitsvalidierung](../../../../docs/framework/wcf/samples/security-validation.md) Beispiel.)  
  
     [!code-csharp[LockdownValidation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorelement.cs#3)]  
  
3.  Stellen Sie sicher, dass die kompilierte Assembly mit einem starken Namen signiert wird. Weitere Informationen finden Sie unter den [Strong Name-Tool ("sn". EXE-Datei)](https://go.microsoft.com/fwlink/?LinkId=248217) und den Compilerbefehlen für Ihre Sprache.  
  
### <a name="to-install-the-validator-into-the-target-computer"></a>So installieren Sie die Bestätigung auf dem Zielcomputer  
  
1.  Installieren Sie die Endpunktbestätigung mithilfe des entsprechenden Mechanismus. In einem Unternehmen kann dies die Verwendung der Gruppenrichtlinie und des Systems Management Server (SMS) sein.  
  
2.  Installieren Sie die Assembly mit starkem Namen, in dem global Assembly Cache mithilfe der [Gacutil.exe (Global Assembly Cache Tool)](https://msdn.microsoft.com/library/ex0ss12c\(v=vs.110\).aspx).  
  
3.  Verwenden Sie die <xref:System.Configuration?displayProperty=nameWithType>-Namespacetypen, um Folgendes durchzuführen:  
  
    1.  Hinzufügen die Erweiterung für die [ \<BehaviorExtensions >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md) mit einem vollständig qualifizierten Typnamen und Sperren Sie das Element.  
  
         [!code-csharp[LockdownValidation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#5)]  
  
    2.  Fügen Sie das verhaltenselement der `EndpointBehaviors` Eigenschaft der [ \<CommonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) und Sperren Sie das Element. (Um eine Bestätigung auf der Dienstseite zu installieren, muss die Bestätigung ein <xref:System.ServiceModel.Description.IServiceBehavior> sein und zur `ServiceBehaviors`-Eigenschaft hinzugefügt werden.) Das folgende Codebeispiel veranschaulicht die ordnungsgemäße Konfiguration nach den Schritten a. und b. Der einzige Unterschied ist, dass hier kein starker Name vergeben wird.  
  
         [!code-csharp[LockdownValidation#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#6)]  
  
    3.  Speichern Sie die Datei machine.config. Das folgende Codebeispiel führt alle Aufgaben in Schritt 3 durch, speichert aber eine lokale Kopie der geänderten Datei machine.config.  
  
         [!code-csharp[LockdownValidation#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#7)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht, wie ein gemeinsames Verhalten zu einer machine.config-Datei hinzugefügt und wie eine Kopie auf der Festplatte gespeichert wird. Die `InternetClientValidatorBehavior` stammt aus dem [Sicherheitsvalidierung](../../../../docs/framework/wcf/samples/security-validation.md) Beispiel.  
  
 [!code-csharp[LockdownValidation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#1)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Sie können darüber hinaus die Elemente der Konfigurationsdatei verschlüsseln. Weitere Informationen finden Sie im Abschnitt "Siehe auch".  
  
## <a name="see-also"></a>Siehe auch  
 [Verschlüsseln von konfigurationsdateielementen mit DPAPI](https://go.microsoft.com/fwlink/?LinkId=94954)  
 [Verschlüsseln von konfigurationsdateielementen mit RSA](https://go.microsoft.com/fwlink/?LinkId=94955)
