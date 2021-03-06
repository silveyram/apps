---

copyright:

  years: 2014, 2017, 2018

lastupdated: "2018-01-18"

---

{:shortdesc: .shortdesc}

# Sicherheitsbereitstellung für {{site.data.keyword.Bluemix_notm}}
{: #security-deployment}

Die Architektur der Sicherheitsbereitstellung für {{site.data.keyword.Bluemix_notm}} umfasst unterschiedliche Informationsflüsse für App-Benutzer und Entwickler, um sicheren Zugriff sicherzustellen.

![{{site.data.keyword.Bluemix_notm}} - Architektur der Sicherheitsbereitstellung](images/sec_deployment.svg)

Abbildung 1. Architektur der Sicherheitsbereitstellung für {{site.data.keyword.Bluemix_notm}}

## Ablauf der Benutzeranmeldung
{: #user-login}

Für Benutzer der {{site.data.keyword.Bluemix_notm}}-*App* ist der **Ablauf des App-Benutzers** wie folgt:
 1. Über eine Firewall mit aktivem Abwehren unbefugter Zugriffe und aktiver Netzsicherheit.
 2. Über das IBM DataPower Gateway mit Reverse Proxy und SSL-Terminierungsproxy.
 3. Über den Netzrouter.
 4. Erreichen der Anwendungslaufzeit im Droplet Execution Agent (DEA).

Der {{site.data.keyword.Bluemix_notm}}-*Entwickler* folgt zwei Hauptabläufen: einem für die Anmeldung und einem für die Entwicklung und Bereitstellung.

## Ablauf der Entwickleranmeldung
{: #dev-login}

Für Entwickler, die sich bei {{site.data.keyword.Bluemix_notm}} Public anmelden, sieht der Ablauf wie folgt aus:
      1. Über den Service IBM Single Sign On.
      2. Über eine IBM Webidentität.
    * Für Entwickler, die sich bei {{site.data.keyword.Bluemix_notm}} Dedicated oder Local anmelden, erfolgt der Ablauf über das Unternehmens-LDAP.

### Entwicklungs- und
Bereitstellungsablauf
{: #dev-dep-login}

1. Über eine Firewall mit aktivem Abwehren unbefugter Zugriffe und aktiver Netzsicherheit. Dies gilt nur für {{site.data.keyword.Bluemix_notm}} Dedicated.
2. Über das IBM DataPower Gateway mit Reverse Proxy und SSL-Terminierungsproxy.
3. Über den Netzrouter.
4. Über die Autorisierung über einen Cloud Foundry-Cloud-Controller, um einen Zugriff sicherzustellen, der auf die Apps und Serviceinstanzen beschränkt ist, die von dem Entwickler erstellt wurden.

### Ablauf bei Dedicated und Local
{: #dedicate-loc-login}

Für *Administratoren* von {{site.data.keyword.Bluemix_notm}} Dedicated und {{site.data.keyword.Bluemix_notm}} Local ist der **Ablauf für Administratoren** wie folgt:
1. Über eine Firewall mit aktivem Abwehren unbefugter Zugriffe und aktiver Netzsicherheit.
2. Über das IBM DataPower Gateway mit Reverse Proxy und SSL-Terminierungsproxy.
3. Über den Netzrouter.
4. Erreichen der Verwaltungsseite in der {{site.data.keyword.Bluemix_notm}}-Benutzerschnittstelle.

Zusätzlich zu den in diesen Pfaden beschriebenen Benutzern führt ein autorisiertes Sicherheitsoperationsteam von IBM verschiedene Tasks zur Betriebssicherheit durch, z. B. Folgendes:
 * Scans auf Sicherheitslücken. Bei {{site.data.keyword.Bluemix_notm}} Local obliegt die physische Sicherheit der lokalen Instanz und alle Überprüfungen in Ihrer Firewall Ihrer Zuständigkeit.
 * Benutzerzugriffsmanagement.
 * Abschottung des Betriebssystems durch regelmäßiges Anwenden von Fixes mithilfe von IBM Endpoint Manager.
 * Risikomanagement mit Schutz gegen Angriffe von außen.
 * Sicherheitsüberwachung mit QRadar.
 * Über die Verwaltungsseite verfügbare Sicherheitsberichte.
