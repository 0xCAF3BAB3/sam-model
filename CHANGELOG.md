# Changelog

## AMLmodel_v1
 * Initial version.

## AMLmodel_v2
 * Removed InterfaceClassLib "CommunicationInterfaceClassLib".
 * Adapted RoleClassLib "CommunicationRoleClassLib" to match new code-architecture (see commit https://bitbucket.org/0xCAF3BAB3/pushlistener-code-architecture/commits/e6b610886daff5da449919eb8ef27b1caac29e37).
 * Adapted InstanceHierarchy to the above changes.

## AMLmodel_v3
 * Removed BusinessRoleClassLib and its assignments in InstanceHierarchy because it is currently not used for code-generation.
 * Renamed IH IE "PushListenerSystem" in "Service".
 * Renamed IH IEs "Node1", "Node2" and "Node3" in "Component1", "Component2" and "Component3".
 * Renamed IE "CommunicationPorts" (located inside every component) in "Ports".
 * Adapted RoleClassLib "CommunicationRoleClassLib":
	- IE "Port" is not divided into Receiver and Sender and its concrete implementations anymore like it was in AMLmodel_v2.
	- Instead, IE "Port" is directly assigned to every port.
	- nd an additional IE "PortStyle" is assigned to every port to indicate communication-style (Rmi, Udp, etc.).
	- And an additional IE "PortType" is assigned to every port to indicate communication-type (Receiver, Sender, etc.).
	- And an additional IE "PortParameters" is assigned to every port, which holds further communication-configuration-parameters (Rmi parameters, Udp parameters, etc.); e.g. PortParameters.Rmi.hostname or PortParameters.Rmi.portRegistry
	- --> Better global view instead of very specialized view.
 * Adapted InstanceHierarchy to the above changes.

## AMLmodel_v4
 * Renamed set attribute-values in IH for RC "PortProperties" starting with "Rmi" to starting with "rmi".
 * Adapted RC "MessageModel": has no Sub-RCs anymore and instead added an attribute "name".
 * Adapted RC "PortStyle": has no Sub-RCs anymore and instead added an attribute "style".
 * Adapted InstanceHierarchy to the above changes.