---
UID : NA:ks
ms.assetid : fb465859-7c13-31ab-a4d2-3642a43e1ae8
ms.author : windowsdriverdev
ms.date : 01/18/18
ms.keywords : 
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : portal
---

# ks.h header



ks.h contains the following programming interfaces:



## Interfaces
| Title | Description |
| ---- |:---- |
| [IKsControl](nn-ks-ikscontrol.md) | The IKsControl interface is a COM-style interface implemented on AVStream filters and pins. |
| [IKsDeviceFunctions](nn-ks-iksdevicefunctions.md) | The IKsDeviceFunctions interface is a COM-style interface implemented on AVStream devices. This interface is available in Windows Server 2003 SP1 and later versions of Windows. |
| [IKsReferenceClock](nn-ks-iksreferenceclock.md) | The IKsReferenceClock interface is a COM-style interface that is provided by AVStream on all pins. The pin passes the request onto the master clock. |


## IOCTLs
| Title | Description |
| ---- |:---- |
| [IOCTL_KS_DISABLE_EVENT](ni-ks-ioctl_ks_disable_event.md) | An application can use IOCTL_KS_DISABLE_EVENT to rescind a previous request notification. The application specifies IOCTL_KS_DISABLE_EVENT in the IoControl parameter of a call to KsSynchronousDeviceControl. |
| [IOCTL_KS_ENABLE_EVENT](ni-ks-ioctl_ks_enable_event.md) | An application can use IOCTL_KS_ENABLE_EVENT to request notification of a KS event type, or to determine the events supported by a KS object. |
| [IOCTL_KS_HANDSHAKE](ni-ks-ioctl_ks_handshake.md) | A kernel-mode client can use IOCTL_KS_HANDSHAKE to negotiate an interface between unconnected AVStream pins. |
| [IOCTL_KS_METHOD](ni-ks-ioctl_ks_method.md) | An application can use IOCTL_KS_METHOD to execute a method on a KS object. The application passes IOCTL_KS_METHOD with the parameters described below to the KsSynchronousDeviceControl function. |
| [IOCTL_KS_PROPERTY](ni-ks-ioctl_ks_property.md) | An application can use IOCTL_KS_PROPERTY to get or set properties, or to determine the properties supported by a KS object. The application passes IOCTL_KS_PROPERTY with the parameters described below to the KsSynchronousDeviceControl function. |
| [IOCTL_KS_READ_STREAM](ni-ks-ioctl_ks_read_stream.md) | An application can use IOCTL_KS_READ_STREAM to read data from a pin. The application passes IOCTL_KS_READ_STREAM with the parameters described below to the KsSynchronousDeviceControl function. |
| [IOCTL_KS_RESET_STATE](ni-ks-ioctl_ks_reset_state.md) | An application can use IOCTL_KS_RESET_STATE to return a pin to the state it was in at Acquire-time. The application passes IOCTL_KS_RESET_STATE with the parameters described below to the KsSynchronousDeviceControl function. |
| [IOCTL_KS_WRITE_STREAM](ni-ks-ioctl_ks_write_stream.md) | An application can use IOCTL_KS_WRITE_STREAM to write data to a pin. The application passes IOCTL_KS_WRITE_STREAM with the parameters described below to the KsSynchronousDeviceControl function. |


## Functions
| Title | Description |
| ---- |:---- |
| [PFNALLOCATOR_ALLOCATEFRAME](nc-ks-pfnallocator_allocateframe.md) | The KStrAllocateFrame routine describes a vendor-supplied frame allocation function. |
| [PFNALLOCATOR_FREEFRAME](nc-ks-pfnallocator_freeframe.md) | The KStrFreeFrame routine describes a vendor-supplied frame deallocation function. |
| [PFNDEREFERENCEDEVICEOBJECT](nc-ks-pfndereferencedeviceobject.md) | The driver can use this routine to decrement the reference count of the PDO. |
| [PFNKSADDEVENT](nc-ks-pfnksaddevent.md) | An AVStream minidriver's AVStrMiniAddEvent routine is called when a client registers to be notified of an event. This routine is optional. |
| [PFNKSALLOCATOR](nc-ks-pfnksallocator.md) | Minidrivers can optionally supply a callback function of type PFNKSALLOCATOR as a parameter in calls to KsEnableEventWithAllocator, KsPropertyHandlerWithAllocator, and KsMethodHandlerWithAllocator. |
| [PFNKSCANCELTIMER](nc-ks-pfnkscanceltimer.md) | A streaming minidriver's KStrCancelTimer routine is called to cancel a custom timer object that was previously specified in the SetTimer parameter in a call to KsAllocateDefaultClockEx. |
| [PFNKSCLOCK_CORRELATEDTIME](nc-ks-pfnksclock_correlatedtime.md) | KStrClockGetCorrelatedTime is a system-supplied routine that retrieves both the current system time and the corresponding clock tick count since boot. |
| [PFNKSCLOCK_GETTIME](nc-ks-pfnksclock_gettime.md) | KStrClockGetTime is a system-supplied routine that retrieves the current system time. |
| [PFNKSCONTEXT_DISPATCH](nc-ks-pfnkscontext_dispatch.md) | A streaming minidriver's KStrContextDispatch routine is called to process IRP_MJ_POWER IRPs. |
| [PFNKSCORRELATEDTIME](nc-ks-pfnkscorrelatedtime.md) | A streaming minidriver's KStrCorrelatedTime routine is called to retrieve both the presentation time and physical time in a correlated manner. This allows the clock owner to completely determine the current time. |
| [PFNKSDEFAULTALLOCATE](nc-ks-pfnksdefaultallocate.md) | An AVStream minidriver's AVStrMiniAllocate routine allocates a frame using the allocator specified in the Context parameter. |
| [PFNKSDEFAULTFREE](nc-ks-pfnksdefaultfree.md) | An AVStream minidriver's AVStrMiniAllocatorFreeFrame routine frees the specified frame. |
| [PFNKSDELETEALLOCATOR](nc-ks-pfnksdeleteallocator.md) | An AVStream minidriver's AVStrMiniDeleteAllocator routine deletes the allocator that is associated with a pin. |
| [PFNKSDEVICE](nc-ks-pfnksdevice.md) | An AVStream minidriver's AVStrMiniDevicePostStart routine is called when AVStream performs post-PnP-start processing. Use it to load drivers at start time, for example. Such events then will occur in the context of a worker thread after PnP start. |
| [PFNKSDEVICECREATE](nc-ks-pfnksdevicecreate.md) | An AVStream minidriver's AVStrMiniDeviceAdd routine notifies the minidriver that AVStream's PnP AddDevice routine has completed. |
| [PFNKSDEVICEIRP](nc-ks-pfnksdeviceirp.md) | An AVStream minidriver's IRP handler routine is called when these IRPs is dispatched by the device.IRP_MN_QUERY_REMOVE_DEVICEIRP_MN_QUERY_STOP_DEVICEIRP_MN_QUERY_INTERFACE |
| [PFNKSDEVICEIRPVOID](nc-ks-pfnksdeviceirpvoid.md) | An AVStream minidriver's IRP handling routine is called when these IRPs are dispatched by the device.IRP_MN_CANCEL_STOP_DEVICEIRP_MN_CANCEL_REMOVE_DEVICEIRP_MN_REMOVE_DEVICEIRP_MN_STOP_DEVICEIRP_MN_SURPRISE_REMOVAL |
| [PFNKSDEVICEPNPSTART](nc-ks-pfnksdevicepnpstart.md) | An AVStream minidriver's AVStrMiniDeviceStart routine is called when an IRP_MN_START_DEVICE request is sent for a specified device. |
| [PFNKSDEVICEQUERYCAPABILITIES](nc-ks-pfnksdevicequerycapabilities.md) | An AVStream minidriver's AVStrMiniDeviceQueryCapabilities routine is called when an IRP_MN_QUERY_CAPABILITIES is dispatched by the device. |
| [PFNKSDEVICEQUERYPOWER](nc-ks-pfnksdevicequerypower.md) | AVStream calls a minidriver's AVStrMiniDeviceQueryPower routine when it receives an IRP_MN_QUERY_POWER request. |
| [PFNKSDEVICESETPOWER](nc-ks-pfnksdevicesetpower.md) | AVStream calls a minidriver's AVStrMiniDeviceSetPower routine when it receives an IRP_MN_SET_POWER. |
| [PFNKSFASTHANDLER](nc-ks-pfnksfasthandler.md) | KStrFastHandler is a driver-supplied routine that handles a property or method request without the creation of an IRP. |
| [PFNKSFILTERIRP](nc-ks-pfnksfilterirp.md) | An AVStream minidriver's AVStrMiniFilterCreate routine is called when a filter receives an IRP. |
| [PFNKSFILTERPROCESS](nc-ks-pfnksfilterprocess.md) | An AVStream minidriver's AVStrMiniFilterProcess routine is called when the filter is meant to process frames. It is used to perform Filter-Centric Processing. |
| [PFNKSFILTERVOID](nc-ks-pfnksfiltervoid.md) | An AVStream minidriver's AVStrMiniFilterReset routine is called when AVStream receives an IOCTL_KS_RESET_STATE to return the filter to the state it was in at Acquire-time. |
| [PFNKSHANDLER](nc-ks-pfnkshandler.md) | The minidriver-provided KStrMethodHandler routine is called when Kernel Streaming receives an IOCTL_KS_METHOD. Provide a pointer to this handler in the relevant KSMETHOD_ITEM structure. |
| [PFNKSINTERSECTHANDLER](nc-ks-pfnksintersecthandler.md) | A streaming minidriver's KStrIntersectHandler routine is called to compare a data range to determine if there is an intersection, and if so, the data format of the intersection. |
| [PFNKSINTERSECTHANDLEREX](nc-ks-pfnksintersecthandlerex.md) | AVStream calls a minidriver's AVStrMiniIntersectHandlerEx routine to determine the highest quality intersection of two data ranges. |
| [PFNKSIRPLISTCALLBACK](nc-ks-pfnksirplistcallback.md) | A streaming minidriver's KStrIrpListCallback routine is called to determine whether the passed in IRP should be moved from the source list to the destination list, or if IRP enumeration should be terminated. |
| [PFNKSITEMFREECALLBACK](nc-ks-pfnksitemfreecallback.md) | A streaming minidriver's KStrItemFreeCallback routine is called to free a previously allocated create item. KStrItemFreeCallback allows the minidriver to perform any cleanup, including flushing security descriptor changes, if necessary. |
| [PFNKSPIN](nc-ks-pfnkspin.md) | An AVStream minidriver's callback routine is called when: There is data available for a KSPIN structure to process. Use this routine to perform Pin-Centric Processing.The relevant KSPIN is serving as a sink pin and is connected to an AVStream source pin. |
| [PFNKSPINFRAMERETURN](nc-ks-pfnkspinframereturn.md) | An AVStream minidriver's AVStrMiniFrameReturn routine is called when an injected frame has completed its trip around the circuit and is ready to be recycled or freed. |
| [PFNKSPINHANDSHAKE](nc-ks-pfnkspinhandshake.md) | An AVStream minidriver's AVStrMiniPinHandshake routine is called when AVStream receives a protocol handshake request that it does not handle. |
| [PFNKSPININITIALIZEALLOCATOR](nc-ks-pfnkspininitializeallocator.md) | An AVStream minidriver's AVStrMiniInitializeAllocator routine initializes an allocator that will be associated with a pin. |
| [PFNKSPINIRP](nc-ks-pfnkspinirp.md) | An AVStream minidriver's routine is called when an activity on the pin is performed and it receives these IRPs:IRP_MJ_CREATEIRP_MJ_CLOSE |
| [PFNKSPINIRPCOMPLETION](nc-ks-pfnkspinirpcompletion.md) | An AVStream minidriver's AVStrMiniPinIrpCompletion routine is called when an IRP completes a pass around the circuit and the frame that is associated with the IRP is about to be recycled or retired. |
| [PFNKSPINPOWER](nc-ks-pfnkspinpower.md) | An AVStream minidriver's AVStrMiniPinPower routine is called for pin-centric pins when the device is waking or entering a sleep state. |
| [PFNKSPINSETDATAFORMAT](nc-ks-pfnkspinsetdataformat.md) | An AVStream minidriver's AVStrMiniPinSetDataFormat routine is called at pin creation time to verify that the previously agreed upon data format is acceptable for this KSPIN structure and a match for this KSDATARANGE structure. |
| [PFNKSPINSETDEVICESTATE](nc-ks-pfnkspinsetdevicestate.md) | An AVStream minidriver's AVStrMiniPinSetDeviceState routine is called when the state of a KSPIN structure is changed due to the arrival of a connection state property 'set' IOCTL. |
| [PFNKSPINVOID](nc-ks-pfnkspinvoid.md) | An AVStream minidriver's callback routine is called when:The relevant KSPIN is serving as a sink pin and this sink pin is disconnected from an AVStream source pin.A KSPIN structure's reset state is changed due to the arrival of an IOCTL_KS_RESET_STATE device control. This routine is also called when the queue associated with the given pin is flushed. |
| [PFNKSREMOVEEVENT](nc-ks-pfnksremoveevent.md) | An AVStream minidriver's AVStrMiniRemoveEvent routine is called when a client requests to be removed from the notification queue for an event. This routine is optional. |
| [PFNKSSETTIMER](nc-ks-pfnkssettimer.md) | A streaming minidriver's KStrSetTimer routine is called to generate DPC timer callbacks based on presentation time. |
| [PFNKSSTREAMPOINTER](nc-ks-pfnksstreampointer.md) | AVStream calls a minidriver's AVStrMiniCancelCallback routine when the IRP that is associated with a cloned stream pointer is canceled. This routine is optional. |
| [PFNQUERYREFERENCESTRING](nc-ks-pfnqueryreferencestring.md) | This routine creates a buffer from the paged pool and copies the reference string associated with the PDO into this buffer. It is the caller's responsibility to free the buffer using ExFreePool. |
| [PFNREFERENCEDEVICEOBJECT](nc-ks-pfnreferencedeviceobject.md) | The driver can use this routine to increment the reference count of the PDO. |
| [_KsEdit](nf-ks-_ksedit.md) | The _KsEdit function guarantees that a given item is dynamically allocated and associated with an AVStream object through the object bag. |
| [KsAcquireCachedMdl](nf-ks-ksacquirecachedmdl.md) | This function is used to acquire the MDL cached by the KS port driver. The function is used by a kernel mode driver to acquire the MDL for a pipeline-supplied sample generated by an Avstream driver. |
| [KsAcquireControl](nf-ks-ksacquirecontrol.md) | The KsAcquireControl function acquires the filter control mutex for Object. |
| [KsAcquireDevice](nf-ks-ksacquiredevice.md) | The KsAcquireDevice function gains synchronous access for Device by acquiring the device mutex. |
| [KsAcquireDeviceSecurityLock](nf-ks-ksacquiredevicesecuritylock.md) | The KsAcquireDeviceSecurityLock function acquires the security lock associated with a device object. |
| [KsAcquireResetValue](nf-ks-ksacquireresetvalue.md) | The KsAcquireResetValue function retrieves the current reset state from an IOCTL_KS_RESET_STATE IRP. |
| [KsAddDevice](nf-ks-ksadddevice.md) | The KsAddDevice function is the default AddDevice handler installed by KsInitializeDriver. |
| [KsAddEvent](nf-ks-ksaddevent.md) | The KsAddEvent function adds an event to Object's event list. |
| [KsAddIrpToCancelableQueue](nf-ks-ksaddirptocancelablequeue.md) | The KsAddIrpToCancelableQueue function adds an IRP to a queue of cancelable IRPs, thus allowing the IRP to be canceled. If the IRP had been previously set to a canceled state, the KsAddIrpToCancelableQueue function completes the canceling of that IRP. |
| [KsAddItemToObjectBag](nf-ks-ksadditemtoobjectbag.md) | The KsAddItemToObjectBag function adds an object or block of memory to the given object bag. |
| [KsAddObjectCreateItemToDeviceHeader](nf-ks-ksaddobjectcreateitemtodeviceheader.md) | The KsAddObjectCreateItemToDeviceHeader function adds the specified create-item to an empty item in the previously allocated create item list for this device header. |
| [KsAddObjectCreateItemToObjectHeader](nf-ks-ksaddobjectcreateitemtoobjectheader.md) | The KsAddObjectCreateItemToObjectHeader function adds the specified create-item to an empty item in the previously allocated create item list for this object header. |
| [KsAllocateDefaultClock](nf-ks-ksallocatedefaultclock.md) | The KsAllocateDefaultClock function allocates and initializes the default clock structure. |
| [KsAllocateDefaultClockEx](nf-ks-ksallocatedefaultclockex.md) | The KsAllocateDefaultClockEx function allocates and initializes the default clock structure. |
| [KsAllocateDeviceHeader](nf-ks-ksallocatedeviceheader.md) | The KsAllocateDeviceHeader function allocates and initializes the required device extension header. |
| [KsAllocateExtraData](nf-ks-ksallocateextradata.md) | The KsAllocateExtraData function is used with streaming IRPs to allocate a buffer to contain additional header data. A pointer to the allocated buffer is returned, and the buffer must eventually be freed by the caller. |
| [KsAllocateObjectBag](nf-ks-ksallocateobjectbag.md) | The KsAllocateObjectBag function creates an object bag and associates it with a KSDEVICE. |
| [KsAllocateObjectCreateItem](nf-ks-ksallocateobjectcreateitem.md) | The KsAllocateObjectCreateItem function allocates a slot for the specified create item, optionally allocating space for and copying the create item data as well. |
| [KsAllocateObjectHeader](nf-ks-ksallocateobjectheader.md) | The KsAllocateObjectHeader function initializes the required file context header. |
| [KsCacheMedium](nf-ks-kscachemedium.md) | The KsCacheMedium function improves graph building performance of pins that use Mediums to define connectivity. |
| [KsCancelIo](nf-ks-kscancelio.md) | The KsCancelIo function cancels all IRPs on the specified cancel list. If an IRP on the list does not have a cancel routine, only the cancel bit is set in the IRP. The function can be called at IRQ level DISPATCH_LEVEL or lower. |
| [KsCompletePendingRequest](nf-ks-kscompletependingrequest.md) | The KsCompletePendingRequest function is used to complete an I/O request in response to which an AVStream dispatch function previously returned STATUS_PENDING. |
| [KsCopyObjectBagItems](nf-ks-kscopyobjectbagitems.md) | The KsCopyObjectBagItems function copies all items from one object bag into another. |
| [KsCreateAllocator](nf-ks-kscreateallocator.md) | The KsCreateAllocator function creates a handle to an allocator for the given sink connection handle. This function does not complete the IRP or set the status in the IRP. |
| [KsCreateAllocator2](nf-ks-kscreateallocator2.md) | Creates a handle to an allocator for the given sink connection handle. This function does not complete the IRP or set the status in the IRP. |
| [KsCreateClock](nf-ks-kscreateclock.md) | The KsCreateClock function creates a handle to a clock instance. |
| [KsCreateClock2](nf-ks-kscreateclock2.md) | Creates a handle to a clock instance. Call this function after the Component Object Model (COM) is initialized. |
| [KsCreateDefaultAllocator](nf-ks-kscreatedefaultallocator.md) | Given a validated IRP_MJ_CREATE request, the KsCreateDefaultAllocator function creates a default allocator that uses the specified memory pool and associates the IoGetCurrentIrpStackLocation(Irp)-&gt;FileObject with the allocator using an internal dispatch table (KSDISPATCH_TABLE). |
| [KsCreateDefaultAllocatorEx](nf-ks-kscreatedefaultallocatorex.md) | Creates a default allocator that uses the specified memory pool and associates the IoGetCurrentIrpStackLocation(pIrp)-&gt;FileObject with this allocator using an internal dispatch table (KSDISPATCH_TABLE). |
| [KsCreateDefaultClock](nf-ks-kscreatedefaultclock.md) | Given an IRP_MJ_CREATE request, the KsCreateDefaultClock function creates a default clock that uses the system clock as a time base and associates the IoGetCurrentIrpStackLocation(Irp)-&gt;FileObject with the clock using an internal dispatch table (KSDISPATCH_TABLE). Does not complete the IRP or set the status in the IRP.The KsCreateDefaultClock function can only be called at PASSIVE_LEVEL. |
| [KsCreateDefaultSecurity](nf-ks-kscreatedefaultsecurity.md) | The KsCreateDefaultSecurity function creates a security descriptor with default security, optionally inheriting parameters from a parent security descriptor. |
| [KsCreateDevice](nf-ks-kscreatedevice.md) | The KsCreateDevice function creates an AVStream device. |
| [KsCreateFilterFactory](nf-ks-kscreatefilterfactory.md) | The KsCreateFilterFactory function adds a filter factory to a given device. |
| [KsCreatePin](nf-ks-kscreatepin.md) | The KsCreatePin function passes a connection request to a device, creating a pin instance. This function can only be called at PASSIVE_LEVEL for kernel-mode clients. |
| [KsCreatePin2](nf-ks-kscreatepin2.md) | Passes a connection request to a device, creating a pin instance. |
| [KsCreateTopologyNode](nf-ks-kscreatetopologynode.md) | The KsCreateTopologyNode function creates a handle to a topology node instance. The function can only be called at PASSIVE_LEVEL. |
| [KsCreateTopologyNode2](nf-ks-kscreatetopologynode2.md) | Creates a handle to a topology node instance. |
| [KsDecrementCountedWorker](nf-ks-ksdecrementcountedworker.md) | Decrements the current worker count of a worker previous created by KsRegisterCountedWorker. This should be called after each task within a worker has been completed. |
| [KsDefaultAddEventHandler](nf-ks-ksdefaultaddeventhandler.md) | The KsDefaultAddEventHandler function is a default routine to handle event 'add' requests. |
| [KsDefaultDeviceIoCompletion](nf-ks-ksdefaultdeviceiocompletion.md) | The KsDefaultDeviceIoCompletion function is used to return a default response and to complete any device I/O control. |
| [KsDeleteFilterFactory](nf-ks-ksdeletefilterfactory.md) | KsDeleteFilterFactory deletes a given filter factory. |
| [KsDereferenceBusObject](nf-ks-ksdereferencebusobject.md) | Dereferences the bus Physical Device Object. |
| [KsDeviceGetBusData](nf-ks-ksdevicegetbusdata.md) | The KsDeviceGetBusData function reads data from the bus where the given AVStream device resides. |
| [KsDeviceGetFirstChildFilterFactory](nf-ks-ksdevicegetfirstchildfilterfactory.md) | The KsDeviceGetFirstChildFilterFactory function returns the first child filter factory belonging to a given AVStream device. |
| [KsDeviceGetOuterUnknown](nf-ks-ksdevicegetouterunknown.md) | The KsDeviceGetOuterUnknown function returns the outer IUnknown of the AVStream device specified by Device. |
| [KsDeviceRegisterAdapterObject](nf-ks-ksdeviceregisteradapterobject.md) | The KsDeviceRegisterAdapterObject function registers a DMA adapter object with AVStream for performing scatter/gather DMA on the specified device. All drivers compiled for Win64 should use IKsDeviceFunctions::RegisterAdapterObjectEx instead. |
| [KsDeviceRegisterAggregatedClientUnknown](nf-ks-ksdeviceregisteraggregatedclientunknown.md) | This inline function is a wrapper for KsRegisterAggregatedClientUnknown. |
| [KsDeviceRegisterThermalDispatch](nf-ks-ksdeviceregisterthermaldispatch.md) | This function is used by the Avstream miniport driver to register callbacks for thermal notifications with the KS port driver. |
| [KsDeviceSetBusData](nf-ks-ksdevicesetbusdata.md) | The KsDeviceSetBusData function writes data to the bus on which the specified AVStream device resides. |
| [KsDisableEvent](nf-ks-ksdisableevent.md) | The KsDisableEvent function disables events requested through IOCTL_KS_DISABLE_EVENT. |
| [KsDiscard](nf-ks-ksdiscard.md) | The KsDiscard macro removes a given item from an object bag. |
| [KsDiscardEvent](nf-ks-ksdiscardevent.md) | The KsDiscardEvent function discards the memory used by an event entry after the objects have been dereferenced. |
| [KsDispatchFastIoDeviceControlFailure](nf-ks-ksdispatchfastiodevicecontrolfailure.md) | The KsDispatchFastIoDeviceControlFailure function is used in a KSDISPATCH_TABLE.FastDeviceIoControl entry that are not handled. The function should always return FALSE. |
| [KsDispatchFastReadFailure](nf-ks-ksdispatchfastreadfailure.md) | The KsDispatchFastReadFailure function is used in a KSDISPATCH_TABLE.FastRead entry when fast I/O read is not handled. The function should always return FALSE. |
| [KsDispatchInvalidDeviceRequest](nf-ks-ksdispatchinvaliddevicerequest.md) | The KsDispatchInvalidDeviceRequest function is used in KSDISPATCH_TABLE entries that are not handled and that need to return STATUS_INVALID_DEVICE_REQUEST. |
| [KsDispatchIrp](nf-ks-ksdispatchirp.md) | KsDispatchIrp calls a dispatch routine corresponding to the function code of the specified IRP. KsDispatchIrp then returns the status code from this call. |
| [KsDispatchQuerySecurity](nf-ks-ksdispatchquerysecurity.md) | The KsDispatchQuerySecurity function is used in the KSDISPATCH_TABLE.QuerySecurity entry to handle querying about the current security descriptor. |
| [KsDispatchSetSecurity](nf-ks-ksdispatchsetsecurity.md) | The KsDispatchSetSecurity function is used in the KSDISPATCH_TABLE.SetSecurity entry to handle setting the current security descriptor. |
| [KsDispatchSpecificMethod](nf-ks-ksdispatchspecificmethod.md) | The KsDispatchSpecificMethod function dispatches a method to a specific handler. The function assumes that the caller has previously dispatched the IRP to a handler through the KsMethodHandler function. The function can only be called at PASSIVE_LEVEL. |
| [KsDispatchSpecificProperty](nf-ks-ksdispatchspecificproperty.md) | The KsDispatchSpecificProperty function dispatches the property to a specific handler. |
| [KsEnableEvent](nf-ks-ksenableevent.md) | The KsEnableEvent function enables events requested through IOCTL_KS_ENABLE_EVENT. It responds to all event identifiers defined by the sets. This function can only be called at PASSIVE_LEVEL. |
| [KsEnableEventWithAllocator](nf-ks-ksenableeventwithallocator.md) | The KsEnableEventWithAllocator function enables events requested through IOCTL_KS_ENABLE_EVENT but also allows an optional allocator callback to be used to provide a buffer for the parameters. |
| [KSEVENT_ENTRY_IRP_STORAGE](nf-ks-ksevent_entry_irp_storage.md) | This macro retrieves a pointer to the KSEVENT_ENTRY structure stored in Irp. |
| [KSEVENT_ITEM_IRP_STORAGE](nf-ks-ksevent_item_irp_storage.md) | This macro retrieves a pointer to the KSEVENT_ITEM structure stored in Irp. |
| [KSEVENT_SET_IRP_STORAGE](nf-ks-ksevent_set_irp_storage.md) | This macro retrieves a pointer to the KSEVENT_SET structure stored in Irp. This information is initialized only for basic support requests; it is not initialized for enable requests. |
| [KsFastMethodHandler](nf-ks-ksfastmethodhandler.md) | The KsFastMethodHandler function handles fast methods requested through IOCTL_KS_METHOD. It responds to all method identifiers defined by the sets that are also contained in the fast I/O list. This function can only be called at PASSIVE_LEVEL. |
| [KsFastPropertyHandler](nf-ks-ksfastpropertyhandler.md) | The KsFastPropertyHandler function handles fast property requests through IOCTL_KS_PROPERTY. It responds to all property identifiers defined by the sets that are also contained in the fast I/O list. This function can only be called at PASSIVE_LEVEL. |
| [KsFilterAcquireControl](nf-ks-ksfilteracquirecontrol.md) | The KsFilterAcquireControl function acquires the filter control mutex for the AVStream filter specified by Filter. |
| [KsFilterAcquireProcessingMutex](nf-ks-ksfilteracquireprocessingmutex.md) | The KsFilterAcquireProcessingMutex function acquires the processing mutex for a specified AVStream filter. |
| [KsFilterAddEvent](nf-ks-ksfilteraddevent.md) | The KsFilterAddEvent function adds an event to Filter's event list. |
| [KsFilterAddTopologyConnections](nf-ks-ksfilteraddtopologyconnections.md) | The KsFilterAddTopologyConnections function adds new topology connections to a filter. |
| [KsFilterAttemptProcessing](nf-ks-ksfilterattemptprocessing.md) | The KsFilterAttemptProcessing function attempts to initiate processing on Filter. |
| [KsFilterCreateNode](nf-ks-ksfiltercreatenode.md) | The KsFilterCreateNode function creates a new topology node on the specified filter. |
| [KsFilterCreatePinFactory](nf-ks-ksfiltercreatepinfactory.md) | The KsFilterCreatePinFactory function creates a new pin factory on the specified filter. |
| [KsFilterFactoryAddCreateItem](nf-ks-ksfilterfactoryaddcreateitem.md) | The KsFilterFactoryAddCreateItem function adds a new create item for the specified filter factory. |
| [KsFilterFactoryGetDevice](nf-ks-ksfilterfactorygetdevice.md) | The KsFilterFactoryGetDevice function returns the AVStream device to which FilterFactory belongs. |
| [KsFilterFactoryGetFirstChildFilter](nf-ks-ksfilterfactorygetfirstchildfilter.md) | The KsFilterFactoryGetFirstChildFilter function returns the first instantiated filter created by FilterFactory. |
| [KsFilterFactoryGetNextSiblingFilterFactory](nf-ks-ksfilterfactorygetnextsiblingfilterfactory.md) | The KsFilterFactoryGetNextSiblingFilterFactory function returns the next filter factory belonging to the parent device of FilterFactory. |
| [KsFilterFactoryGetOuterUnknown](nf-ks-ksfilterfactorygetouterunknown.md) | The KsFilterFactoryGetOuterUnknown function returns the outer IUnknown of the specified filter factory. |
| [KsFilterFactoryGetParentDevice](nf-ks-ksfilterfactorygetparentdevice.md) | The KsFilterFactoryGetParentDevice function returns the parent device of the given filter factory. |
| [KsFilterFactoryGetSymbolicLink](nf-ks-ksfilterfactorygetsymboliclink.md) | The KsFilterFactoryGetSymbolicLink function returns the symbolic link associated with a given filter factory. |
| [KsFilterFactoryRegisterAggregatedClientUnknown](nf-ks-ksfilterfactoryregisteraggregatedclientunknown.md) | This inline function is a wrapper for KsRegisterAggregatedClientUnknown. |
| [KsFilterFactorySetDeviceClassesState](nf-ks-ksfilterfactorysetdeviceclassesstate.md) | The KsFilterFactorySetDeviceClassesState function enables or disables the device classes that have been registered by a given filter factory. |
| [KsFilterFactoryUpdateCacheData](nf-ks-ksfilterfactoryupdatecachedata.md) | The KsFilterFactoryUpdateCacheData function updates the FilterData registry key and the Medium cache (a set of registry keys) for a given filter factory. |
| [KsFilterGenerateEvents](nf-ks-ksfiltergenerateevents.md) | The KsFilterGenerateEvents function generates events of an indicated type that are present in Filter's event list. |
| [KsFilterGetAndGate](nf-ks-ksfiltergetandgate.md) | The KsFilterGetAndGate function returns Filter's AND gate. |
| [KsFilterGetChildPinCount](nf-ks-ksfiltergetchildpincount.md) | The KsFilterGetChildPinCountfunctionreturns the number of pins of a given type that are currently instantiated on a given filter. |
| [KsFilterGetDevice](nf-ks-ksfiltergetdevice.md) | The KsFilterGetDevice function returns the AVStream device to which Filter belongs. |
| [KsFilterGetFirstChildPin](nf-ks-ksfiltergetfirstchildpin.md) | The KsFilterGetFirstChildPin function returns the first instantiated pin of type PinID on the filter specified by Filter. |
| [KsFilterGetNextSiblingFilter](nf-ks-ksfiltergetnextsiblingfilter.md) | The KsFilterGetNextSiblingFilter function returns the next instantiated filter belonging to the parent filter factory of Filter. |
| [KsFilterGetOuterUnknown](nf-ks-ksfiltergetouterunknown.md) | The KsFilterGetOuterUnknown function returns the outer IUnknown interface of the filter specified by Filter. |
| [KsFilterGetParentFilterFactory](nf-ks-ksfiltergetparentfilterfactory.md) | The KsFilterGetParentFilterFactory function returns the parent filter factory of the given filter. |
| [KsFilterRegisterAggregatedClientUnknown](nf-ks-ksfilterregisteraggregatedclientunknown.md) | This inline function is a wrapper for KsRegisterAggregatedClientUnknown. |
| [KsFilterRegisterPowerCallbacks](nf-ks-ksfilterregisterpowercallbacks.md) | The KsFilterRegisterPowerCallbacks function registers power management callbacks for Filter. |
| [KsFilterReleaseControl](nf-ks-ksfilterreleasecontrol.md) | The KsFilterReleaseControl function releases the control mutex for the AVStream filter specified by Filter. |
| [KsFilterReleaseProcessingMutex](nf-ks-ksfilterreleaseprocessingmutex.md) | The KsFilterReleaseProcessingMutex function releases the processing mutex for the AVStream filter specified by Filter. |
| [KsForwardAndCatchIrp](nf-ks-ksforwardandcatchirp.md) | The KsForwardAndCatchIrp function forwards an IRP to the specified driver after initializing the next stack location, and regains control of the IRP on completion from that driver. |
| [KsForwardIrp](nf-ks-ksforwardirp.md) | The KsForwardIrp function forwards an IRP to the specified driver after initializing the next stack location and setting the file object. |
| [KsFreeDefaultClock](nf-ks-ksfreedefaultclock.md) | The KsFreeDefaultClock function frees a default clock structure previously allocated with KsAllocateDefaultClock, taking into account any currently running timer DPCs. |
| [KsFreeDeviceHeader](nf-ks-ksfreedeviceheader.md) | The KsFreeDeviceHeader function cleans up and frees a previously allocated device header. |
| [KsFreeEventList](nf-ks-ksfreeeventlist.md) | The KsFreeEventList function handles freeing all events from a specified list, with the assumption that these events are composed of KSEVENT_ENTRY structures. This function can only be called at PASSIVE_LEVEL. |
| [KsFreeObjectBag](nf-ks-ksfreeobjectbag.md) | The KsFreeObjectBag function empties and frees an object bag. |
| [KsFreeObjectCreateItem](nf-ks-ksfreeobjectcreateitem.md) | Frees the slot for the specified create item. |
| [KsFreeObjectCreateItemsByContext](nf-ks-ksfreeobjectcreateitemsbycontext.md) | Frees all create items with a specific context. |
| [KsFreeObjectHeader](nf-ks-ksfreeobjectheader.md) | The KsFreeObjectHeader function cleans up and frees a previously allocated object header. |
| [KsGateAddOffInputToAnd](nf-ks-ksgateaddoffinputtoand.md) | The KsGateAddOffInputToAnd function adds a new input in the OFF state to a given AND gate. |
| [KsGateAddOffInputToOr](nf-ks-ksgateaddoffinputtoor.md) | The KsGateAddOffInputToOr function adds a new input in the OFF state to a given OR gate. |
| [KsGateAddOnInputToAnd](nf-ks-ksgateaddoninputtoand.md) | The KsGateAddOnInputToAnd function adds a new input in the ON state to a given AND gate. |
| [KsGateAddOnInputToOr](nf-ks-ksgateaddoninputtoor.md) | The KsGateAddOnInputToOr function adds a new input in the ON state to a given OR gate. |
| [KsGateCaptureThreshold](nf-ks-ksgatecapturethreshold.md) | The KsGateCaptureThreshold function is used to capture an ON input of an AND gate specified by Gate. |
| [KsGateGetStateUnsafe](nf-ks-ksgategetstateunsafe.md) | The KsGateGetStateUnsafe function returns the state of the given gate (open or closed) in an unsafe manner, that is without regard to synchronization. |
| [KsGateInitialize](nf-ks-ksgateinitialize.md) | The KsGateInitialize function initializes a gate for use. |
| [KsGateInitializeAnd](nf-ks-ksgateinitializeand.md) | The KsGateInitializeAnd function initializes a KSGATE structure as an AND gate and attaches it to the OR gate specified by NextOrGate. |
| [KsGateInitializeOr](nf-ks-ksgateinitializeor.md) | The KsGateInitializeOr function initializes a KSGATE structure as an OR gate and attaches it to the AND gate specified by NextAndGate. |
| [KsGateRemoveOffInputFromAnd](nf-ks-ksgateremoveoffinputfromand.md) | The KsGateRemoveOffInputFromAnd function removes an existing input that is in the OFF state from an AND gate. |
| [KsGateRemoveOffInputFromOr](nf-ks-ksgateremoveoffinputfromor.md) | The KsGateRemoveOffInputFromOr function removes an existing input that is in the OFF state from an OR gate. |
| [KsGateRemoveOnInputFromAnd](nf-ks-ksgateremoveoninputfromand.md) | The KsGateRemoveOnInputFromAnd function removes an existing input that is in the ON state from an AND gate. |
| [KsGateRemoveOnInputFromOr](nf-ks-ksgateremoveoninputfromor.md) | The KsGateRemoveOnInputFromOr function removes an existing input that is in the ON state from an OR gate. |
| [KsGateTerminateAnd](nf-ks-ksgateterminateand.md) | The KsGateTerminateAnd function deletes an existing AND gate and removes an input from any attached OR gate. |
| [KsGateTerminateOr](nf-ks-ksgateterminateor.md) | The KsGateTerminateOr function deletes an existing OR gate and removes an input from any attached AND gate. |
| [KsGateTurnInputOff](nf-ks-ksgateturninputoff.md) | The KsGateTurnInputOff function turns off an existing input to Gate. |
| [KsGateTurnInputOn](nf-ks-ksgateturninputon.md) | The KsGateTurnInputOn function turns on an existing input to Gate. |
| [KsGenerateDataEvent](nf-ks-ksgeneratedataevent.md) | The KsGenerateDataEvent function generates one of the standard event notifications when given an event entry structure and callback data. |
| [KsGenerateEvent](nf-ks-ksgenerateevent.md) | The KsGenerateEvent function generates a standard event notification given an event entry structure. |
| [KsGenerateEventList](nf-ks-ksgenerateeventlist.md) | The KsGenerateEventList function enumerates the event list and searches for the specified event to generate. |
| [KsGenerateEvents](nf-ks-ksgenerateevents.md) | The KsGenerateEvents function generates events of an indicated type that are present in Object's event list. |
| [KsGenerateThermalEvent](nf-ks-ksgeneratethermalevent.md) | This function is used by clients (miniport drivers) that do not want to subscribe to the thermal manager, but want to do their own thermal management. |
| [KsGetDefaultClockState](nf-ks-ksgetdefaultclockstate.md) | The KsGetDefaultClockState function gets the current state of the clock.The function can be called at DISPATCH_LEVEL. |
| [KsGetDefaultClockTime](nf-ks-ksgetdefaultclocktime.md) | The KsGetDefaultClockTime function gets the current time of the clock.The function can be called at DISPATCH_LEVEL. |
| [KsGetDevice](nf-ks-ksgetdevice.md) | The KsGetDevice function returns the AVStream device structure to which Object belongs. |
| [KsGetDeviceForDeviceObject](nf-ks-ksgetdevicefordeviceobject.md) | The KsGetDeviceForDeviceObject function returns the AVStream device structure for a given functional device object. |
| [KsGetFilterFromFileObject](nf-ks-ksgetfilterfromfileobject.md) | The KsGetFilterFromFileObject function returns the AVStream filter object associated with FileObject. |
| [KsGetFilterFromIrp](nf-ks-ksgetfilterfromirp.md) | The KsGetFilterFromIrp function returns the AVStream filter object associated with a given IRP. |
| [KsGetFirstChild](nf-ks-ksgetfirstchild.md) | The KsGetFirstChild function returns the first AVStream child object of Object. |
| [KsGetImageNameAndResourceId](nf-ks-ksgetimagenameandresourceid.md) | The KsGetImageNameAndResourceId function returns the image name and resource identifier that corresponds to the RegKey handle. |
| [KsGetNextSibling](nf-ks-ksgetnextsibling.md) | The KsGetNextSibling function returns the next sibling of a given object. |
| [KsGetNodeIdFromIrp](nf-ks-ksgetnodeidfromirp.md) | The KsGetNodeIdFromIrp function returns the node ID of the node to which Irp was submitted. |
| [KsGetObjectFromFileObject](nf-ks-ksgetobjectfromfileobject.md) | The KsGetObjectFromFileObject function returns the AVStream object cast to PVOID from FileObject. |
| [KsGetObjectTypeFromFileObject](nf-ks-ksgetobjecttypefromfileobject.md) | The KsGetObjectTypeFromFileObject function returns the AVStream object type that is associated with a given file object. |
| [KsGetObjectTypeFromIrp](nf-ks-ksgetobjecttypefromirp.md) | The KsGetObjectTypeFromIrp function returns the AVStream object type that is associated with a given IRP. |
| [KsGetOuterUnknown](nf-ks-ksgetouterunknown.md) | The KsGetOuterUnknown function returns the outer IUnknown of a given AVStream object. |
| [KsGetParent](nf-ks-ksgetparent.md) | The KsGetParent function acquires the parent of the given object. |
| [KsGetPinFromFileObject](nf-ks-ksgetpinfromfileobject.md) | The KsGetPinFromFileObject function returns the AVStream pin object associated with FileObject. |
| [KsGetPinFromIrp](nf-ks-ksgetpinfromirp.md) | The KsGetPinFromIrp function returns the AVStream pin object associated with the given IRP. |
| [KsHandleSizedListQuery](nf-ks-kshandlesizedlistquery.md) | The KsHandleSizedListQuery function, depending on the length of the system buffer, returns either the size of the buffer needed, number of entries in the specified data list, or copies the entries themselves. |
| [KsIncrementCountedWorker](nf-ks-ksincrementcountedworker.md) | Increments the current worker count, and optionally queues the counted work item with the worker previously created by KsRegisterCountedWorker. |
| [KsInitializeDevice](nf-ks-ksinitializedevice.md) | The KsInitializeDevice function is called by AVStream to initialize the AVStream device class from within KsCreateDevice. |
| [KsInitializeDeviceProfile](nf-ks-ksinitializedeviceprofile.md) | The KsInitializeDeviceProfile API must be called by all miniport drivers to initialize the profile store and publish the device profiles. |
| [KsInitializeDriver](nf-ks-ksinitializedriver.md) | The KsInitializeDriver function initializes the driver object of an AVStream minidriver. |
| [KsLoadResource](nf-ks-ksloadresource.md) | Copies (loads) a resource from the given image. |
| [KsMapModuleName](nf-ks-ksmapmodulename.md) | The KsMapModuleName function returns the image name and resource identifier that corresponds to the PhysicalDeviceObject and ModuleName parameters. |
| [KsMergeAutomationTables](nf-ks-ksmergeautomationtables.md) | The KsMergeAutomationTables function merges two automation tables. |
| [KSMETHOD_ITEM_IRP_STORAGE](nf-ks-ksmethod_item_irp_storage.md) | This macro accesses a pointer to the relevant KSMETHOD_ITEM. Note that this pointer is only set when using KsMethodHandlerWithAllocator. |
| [KSMETHOD_SET_IRP_STORAGE](nf-ks-ksmethod_set_irp_storage.md) | This macro returns a pointer to the KSMETHOD_SET in which the method is located. |
| [KSMETHOD_TYPE_IRP_STORAGE](nf-ks-ksmethod_type_irp_storage.md) | This macro accesses the type of method as described in the KSMETHOD_ITEM. If the method will be processed asynchronously using KsDispatchSpecificMethod, this storage must be maintained intact. |
| [KsMethodHandler](nf-ks-ksmethodhandler.md) | The KsMethodHandler function handles methods requested through IOCTL_KS_METHOD. It works with all method identifiers defined by the sets. The function can only be called at PASSIVE_LEVEL. |
| [KsMethodHandlerWithAllocator](nf-ks-ksmethodhandlerwithallocator.md) | The KsMethodHandlerWithAllocator functions performs the same handling as KsMethodHandler, with the same restrictions, but allows an optional allocator callback to be used to provide a buffer for the parameters. |
| [KsMoveIrpsOnCancelableQueue](nf-ks-ksmoveirpsoncancelablequeue.md) | The KsMoveIrpsOnCancelableQueue function moves the specified IRPs from the SourceList parameter to the DestinationList parameter depending on the value returned from the minidriver-defined KStrIrpListCallback function. |
| [KsNullDriverUnload](nf-ks-ksnulldriverunload.md) | The KsNullDriverUnload function is a default function a driver can use when it has no other tasks to do in its unload function, but must still allow the device to be unloaded by its presence. |
| [KsPersistDeviceProfile](nf-ks-kspersistdeviceprofile.md) | The KsPersistDeviceProfile API commits the profile information to the persistent store. |
| [KsPinAcquireControl](nf-ks-kspinacquirecontrol.md) | The KsPinAcquireControl function acquires the control mutex for the AVStream pin specified by Pin. |
| [KsPinAcquireProcessingMutex](nf-ks-kspinacquireprocessingmutex.md) | The KsPinAcquireProcessingMutex function acquires the processing mutex for the AVStream pin specified by Pin. |
| [KsPinAddEvent](nf-ks-kspinaddevent.md) | The KsPinAddEvent function adds a specified event to Pin's event list. |
| [KsPinAttachAndGate](nf-ks-kspinattachandgate.md) | The KsPinAttachAndGate function connects Pin as an input to a previously initialized AND gate, and connects AndGate as an input to the relevant filter's AND gate. |
| [KsPinAttachOrGate](nf-ks-kspinattachorgate.md) | The KsPinAttachOrGate function connects Pin as an input to a previously initialized OR gate, and connects OrGate as an input to the relevant filter's AND gate. |
| [KsPinAttemptProcessing](nf-ks-kspinattemptprocessing.md) | The KsPinAttemptProcessing function is used to resume processing on a specific pin on a pin-centric filter. It attempts to initiate processing on Pin by sending a processing dispatch call to Pin's processing object. |
| [KsPinDataIntersection](nf-ks-kspindataintersection.md) | The KsPinDataIntersection function handles the KSPROPERTY_PIN_DATAINTERSECTION property through a callback function and performs much of the initial validation of the parameters that are passed. |
| [KsPinDataIntersectionEx](nf-ks-kspindataintersectionex.md) | The KsPinDataIntersectionEx function handles the KSPROPERTY_PIN_DATAINTERSECTION through a callback function. |
| [KsPinGenerateEvents](nf-ks-kspingenerateevents.md) | The KsPinGenerateEvents function generates events of an indicated type that are present in Pin's event list. |
| [KsPinGetAndGate](nf-ks-kspingetandgate.md) | The KsPinGetAndGate function returns the processing control gate for Pin. |
| [KsPinGetAvailableByteCount](nf-ks-kspingetavailablebytecount.md) | The KsPinGetAvailableByteCount routine outputs the number of bytes of input data ahead of the leading edge and the number of bytes of output buffer ahead of the leading edge, both for the queue of a caller-specified pin. |
| [KsPinGetConnectedFilterInterface](nf-ks-kspingetconnectedfilterinterface.md) | The KsPinGetConnectedFilterInterface function queries the filter to which Pin is connected in order to obtain a pointer to a COM interface. |
| [KsPinGetConnectedPinDeviceObject](nf-ks-kspingetconnectedpindeviceobject.md) | The KsPinGetConnectedPinDeviceObject function returns the device object at the top of the device stack corresponding to the sink pin attached to the source pin Pin. |
| [KsPinGetConnectedPinFileObject](nf-ks-kspingetconnectedpinfileobject.md) | The KsPinGetConnectedPinFileObject function returns the file object for the pin to which Pin is connected. Works only for source pins. |
| [KsPinGetConnectedPinInterface](nf-ks-kspingetconnectedpininterface.md) | The KsPinGetConnectedPinInterface function queries the pin to which Pin is connected for a COM style interface. |
| [KsPinGetCopyRelationships](nf-ks-kspingetcopyrelationships.md) | The KsPinGetCopyRelationships function returns copy relationship information for a pin that is contained within a pin-centric filter. |
| [KsPinGetDevice](nf-ks-kspingetdevice.md) | The KsPinGetDevice function returns the AVStream device to which Pin belongs. |
| [KsPinGetFirstCloneStreamPointer](nf-ks-kspingetfirstclonestreampointer.md) | The KsPinGetFirstCloneStreamPointer function returns the first cloned stream pointer on Pin. |
| [KsPinGetLeadingEdgeStreamPointer](nf-ks-kspingetleadingedgestreampointer.md) | The KsPinGetLeadingEdgeStreamPointer function acquires the leading edge stream pointer for the queue associated with the given pin. |
| [KsPinGetNextSiblingPin](nf-ks-kspingetnextsiblingpin.md) | The KsPinGetNextSiblingPin function returns the next instantiated pin of the same type and on the same filter as Pin. |
| [KsPinGetOuterUnknown](nf-ks-kspingetouterunknown.md) | The KsPinGetOuterUnknown function returns the outer IUnknown of the pin specified by Pin. |
| [KsPinGetParentFilter](nf-ks-kspingetparentfilter.md) | The KsPinGetParentFilter function returns the parent filter of Pin. |
| [KsPinGetReferenceClockInterface](nf-ks-kspingetreferenceclockinterface.md) | The KsPinGetReferenceClockInterface function returns a COM style interface to the reference clock associated with Pin. This interface pointer will be an IKsReferenceClock interface. |
| [KsPinGetTrailingEdgeStreamPointer](nf-ks-kspingettrailingedgestreampointer.md) | The KsPinGetTrailingEdgeStreamPointer function acquires the trailing edge stream pointer for the queue associated with the specified pin. |
| [KsPinHandshake](nf-ks-kspinhandshake.md) | The KsPinHandshake function attempts a protocol handshake with a connected pin. |
| [KsPinPropertyHandler](nf-ks-kspinpropertyhandler.md) | The KsPinPropertyHandler function performs standard handling of the static members of the KSPROPSETID_Pin property set. This handling does not include KSPROPERTY_PIN_CINSTANCES or KSPROPERTY_PIN_DATAINTERSECTION. |
| [KsPinRegisterAggregatedClientUnknown](nf-ks-kspinregisteraggregatedclientunknown.md) | This inline function is a wrapper for KsRegisterAggregatedClientUnknown. |
| [KsPinRegisterFrameReturnCallback](nf-ks-kspinregisterframereturncallback.md) | The KsPinRegisterFrameReturnCallback function registers a frame return callback with AVStream for a given pin. |
| [KsPinRegisterHandshakeCallback](nf-ks-kspinregisterhandshakecallback.md) | The KsPinRegisterHandshakeCallback function registers a minidriver-provided callback routine for a given pin. |
| [KsPinRegisterIrpCompletionCallback](nf-ks-kspinregisterirpcompletioncallback.md) | The KsPinRegisterIrpCompletionCallback function registers a minidriver-defined callback routine for a specified pin. |
| [KsPinRegisterPowerCallbacks](nf-ks-kspinregisterpowercallbacks.md) | The KsPinRegisterPowerCallbacks function registers power management callbacks for Pin. |
| [KsPinReleaseControl](nf-ks-kspinreleasecontrol.md) | The KsPinReleaseControl function releases the control mutex for the AVStream pin specified by Pin. |
| [KsPinReleaseProcessingMutex](nf-ks-kspinreleaseprocessingmutex.md) | The KsPinReleaseProcessingMutex function releases the processing mutex for the AVStream pin specified by Pin. |
| [KsPinSetPinClockTime](nf-ks-kspinsetpinclocktime.md) | The KsPinSetPinClockTime function sets the current time on the clock exposed by Pin. |
| [KsPinSubmitFrame](nf-ks-kspinsubmitframe.md) | If a pin has been placed into injection mode by a call to KsPinRegisterFrameReturnCallback, the KsPinSubmitFrame function submits a frame directly into the transport circuit. |
| [KsPinSubmitFrameMdl](nf-ks-kspinsubmitframemdl.md) | If a pin has been placed into injection mode by a call to KsPinRegisterFrameReturnCallback, the KsPinSubmitFrameMdl function submits a frame directly into the transport circuit. |
| [KsProbeStreamIrp](nf-ks-ksprobestreamirp.md) | The KsProbeStreamIrp function makes the specified modifications to the input and output buffers of the given IRP based on the flags passed, and it then validates the stream header. |
| [KsProcessPinUpdate](nf-ks-ksprocesspinupdate.md) | The KsProcessPinUpdate function is called from within a filter-centric filter's AVStrMiniFilterProcess dispatch to update a process pin. |
| [KsPropertyHandler](nf-ks-kspropertyhandler.md) | Drivers call KsPropertyHandler function for IRP handling. |
| [KsPropertyHandlerWithAllocator](nf-ks-kspropertyhandlerwithallocator.md) | The KsPropertyHandlerWithAllocator performs the same handling as KsPropertyHandler, with the same restrictions, but allows an optional allocator callback to be used to provide a buffer for the parameters. |
| [KsPublishDeviceProfile](nf-ks-kspublishdeviceprofile.md) | The KsPublishDeviceProfile API is called to publish device profile information. |
| [KsQueryDevicePnpObject](nf-ks-ksquerydevicepnpobject.md) | The KsQueryDevicePnpObject function returns the PnP device object that can be stored in the device header. This is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if KsDefaultDispatchPnp is used. |
| [KsQueryInformationFile](nf-ks-ksqueryinformationfile.md) | The KsQueryInformationFile function performs an information query against the specified file object. The function attempts to use FastIoDispatch if possible, or it generates an information request against the device object. |
| [KsQueryObjectAccessMask](nf-ks-ksqueryobjectaccessmask.md) | The KsQueryObjectAccessMask function returns the access originally granted to the first client that created a handle on the associated object. Access cannot be changed by duplicating handles. |
| [KsQueryObjectCreateItem](nf-ks-ksqueryobjectcreateitem.md) | The KsQueryObjectCreateItem function returns the create item assigned to the object when created. |
| [KsQueueWorkItem](nf-ks-ksqueueworkitem.md) | The KsQueueWorkItem function queues the specified work item with a worker previous created by the KsRegisterWorker function. |
| [KsReadFile](nf-ks-ksreadfile.md) | The KsReadFile function performs a read against the specified file object. |
| [KsRecalculateStackDepth](nf-ks-ksrecalculatestackdepth.md) | The KsRecalculateStackDepth function recalculates the maximum stack depth required by the underlying device object based on all of the objects that have set a target device (they have added themselves to the object list on the underlying device object using the KsSetTargetDeviceObject function). If the PnP device object has been set on the underlying device header using KsSetDevicePnpAndBaseObject, that device is also taken into account when calculating the maximum stack depth. |
| [KsReferenceBusObject](nf-ks-ksreferencebusobject.md) | References the bus Physical device object. |
| [KsRegisterAggregatedClientUnknown](nf-ks-ksregisteraggregatedclientunknown.md) | In a manner very similar to COM, the KsRegisterAggregatedClientUnknown function aggregates two objects: the specified AVStream object and a client unknown object. |
| [KsRegisterCountedWorker](nf-ks-ksregistercountedworker.md) | Handles clients registering for use of a thread. |
| [KsRegisterFilterWithNoKSPins](nf-ks-ksregisterfilterwithnokspins.md) | The KsRegisterFilterWithNoKSPins function registers with DirectShow filters that have no kernel streaming pins and, therefore, do not stream in kernel mode. |
| [KsRegisterWorker](nf-ks-ksregisterworker.md) | The KsRegisterWorker function handles clients registering for use of a thread. |
| [KsReleaseCachedMdl](nf-ks-ksreleasecachedmdl.md) | The KsReleaseCachedMdl function is used to release the MDL acquired by the KsAcquireCachedMdl call. |
| [KsReleaseControl](nf-ks-ksreleasecontrol.md) | The KsReleaseControl function releases the control mutex for Object. |
| [KsReleaseDevice](nf-ks-ksreleasedevice.md) | The KsReleaseDevice function releases the device mutex and exits the critical region. |
| [KsReleaseDeviceSecurityLock](nf-ks-ksreleasedevicesecuritylock.md) | The KsReleaseDeviceSecurityLock function releases a previously acquired security lock on the device object header. |
| [KsReleaseIrpOnCancelableQueue](nf-ks-ksreleaseirponcancelablequeue.md) | The KsReleaseIrpOnCancelableQueue function releases an acquired IRP that is already on a queue that can be canceled. |
| [KsRemoveIrpFromCancelableQueue](nf-ks-ksremoveirpfromcancelablequeue.md) | The KsRemoveIrpFromCancelableQueue function pops the next noncanceled IRP from the specified queue that can be canceled and removes its cancel status. |
| [KsRemoveItemFromObjectBag](nf-ks-ksremoveitemfromobjectbag.md) | The KsRemoveItemFromObjectBag function removes an item from an object bag. |
| [KsRemoveSpecificIrpFromCancelableQueue](nf-ks-ksremovespecificirpfromcancelablequeue.md) | The KsRemoveSpecificIrpFromCancelableQueue function removes the specified IRP from the specified queue. This is performed on an IRP that was previously acquired using KsRemoveIrpFromCancelableQueue, but that was not actually removed from the queue. |
| [KsSetDefaultClockState](nf-ks-kssetdefaultclockstate.md) | The KsSetDefaultClockState function sets the current state of the clock that is used to reflect the current state of the underlying filter pin. |
| [KsSetDefaultClockTime](nf-ks-kssetdefaultclocktime.md) | The KsSetDefaultClockTime function sets the current time of the clock. |
| [KsSetDevicePnpAndBaseObject](nf-ks-kssetdevicepnpandbaseobject.md) | The KsSetDevicePnpAndBaseObject function sets the PnP device object in the device header, which is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if KsDefaultDispatchPnp is used. |
| [KsSetInformationFile](nf-ks-kssetinformationfile.md) | The KsSetInformationFile function performs an information set against the specified file object. The function attempts to use FastIoDispatch if possible, or it generates an information set against the device object. |
| [KsSetMajorFunctionHandler](nf-ks-kssetmajorfunctionhandler.md) | The KsSetMajorFunctionHandler function sets the handler for a specified major function to use the internal dispatching. |
| [KsSetPowerDispatch](nf-ks-kssetpowerdispatch.md) | Sets the power dispatch function to be called when the driver object receives an IRP_MJ_POWER IRP. |
| [KsSetTargetDeviceObject](nf-ks-kssettargetdeviceobject.md) | The KsSetTargetDeviceObject function sets the target device object of an object. The function adds the object header to a list of object headers that have target devices. |
| [KsSetTargetState](nf-ks-kssettargetstate.md) | Sets the enabled state of a target device associated with the specified object header. |
| [KsStreamIo](nf-ks-ksstreamio.md) | The KsStreamIo function performs a stream read or write against the specified file object. The function attempts to use FastIoDispatch if possible, or it generates a read or write request against the device object. |
| [KsStreamPointerAdvance](nf-ks-ksstreampointeradvance.md) | The KsStreamPointerAdvance function advances a stream pointer to the next data frame. |
| [KsStreamPointerAdvanceOffsets](nf-ks-ksstreampointeradvanceoffsets.md) | The KsStreamPointerAdvanceOffsets function advances the offsets of StreamPointer. |
| [KsStreamPointerAdvanceOffsetsAndUnlock](nf-ks-ksstreampointeradvanceoffsetsandunlock.md) | The KsStreamPointerAdvanceOffsetsAndUnlock function advances StreamPointer the specified number of bytes into the stream (adjusting the OffsetIn and OffsetOut fields of StreamPointer as requested) and unlocks it. |
| [KsStreamPointerCancelTimeout](nf-ks-ksstreampointercanceltimeout.md) | The KsStreamPointerCancelTimeout function cancels a previously scheduled time-out callback on the specified stream pointer. |
| [KsStreamPointerClone](nf-ks-ksstreampointerclone.md) | The KsStreamPointerClone function creates a clone of a given stream pointer. |
| [KsStreamPointerDelete](nf-ks-ksstreampointerdelete.md) | The KsStreamPointerDelete function deletes a clone stream pointer, releasing a reference on the frame to which this stream pointer referred. |
| [KsStreamPointerGetIrp](nf-ks-ksstreampointergetirp.md) | The KsStreamPointerGetIrp function returns the IRP associated with the frame that is referenced by the given stream pointer. |
| [KsStreamPointerGetMdl](nf-ks-ksstreampointergetmdl.md) | The KsStreamPointerGetMdl function returns the MDL associated with the frame referenced by StreamPointer. |
| [KsStreamPointerGetNextClone](nf-ks-ksstreampointergetnextclone.md) | The KsStreamPointerGetNextClone function returns the clone stream pointer that was cloned immediately after the specified clone. |
| [KsStreamPointerLock](nf-ks-ksstreampointerlock.md) | The KsStreamPointerLock function attempts to lock the specified stream pointer. |
| [KsStreamPointerScheduleTimeout](nf-ks-ksstreampointerscheduletimeout.md) | The KsStreamPointerScheduleTimeout function registers a timeout callback with AVStream for the given stream pointer. |
| [KsStreamPointerSetStatusCode](nf-ks-ksstreampointersetstatuscode.md) | The KsStreamPointerSetStatusCode function allows specification of a successful or unsuccessful error code with which to complete the given IRP. |
| [KsStreamPointerUnlock](nf-ks-ksstreampointerunlock.md) | The KsStreamPointerUnlock function unlocks a stream pointer that has previously been locked by an acquisition function (KsGetXxxEdgeStreamPointer) or by KsStreamPointerLock. |
| [KsSynchronousIoControlDevice](nf-ks-kssynchronousiocontroldevice.md) | The KsSynchronousIoControlDevice function performs a synchronous device I/O control on the target device object. It waits in a nonalertable state until the I/O completes. This function can only be called at PASSIVE_LEVEL. |
| [KsTerminateDevice](nf-ks-ksterminatedevice.md) | The KsTerminateDevice function removes an AVStream device. |
| [KsTopologyPropertyHandler](nf-ks-kstopologypropertyhandler.md) | The KsTopologyPropertyHandler function performs standard handling of the static members of the KSPROPSETID_Topology Property Set. The function uses the KSTOPOLOGY structure, which describes the set of information that is returned by this property set. |
| [KsUnregisterWorker](nf-ks-ksunregisterworker.md) | The KsUnregisterWorker function allows clients to unregister a worker. |
| [KsUnserializeObjectPropertiesFromRegistry](nf-ks-ksunserializeobjectpropertiesfromregistry.md) | The KsUnserializeObjectPropertiesFromRegistry function, when given a destination object and a registry path, enumerates the named values and applies them as serialized data to the specified property sets listed in the serialized data. |
| [KsValidateAllocatorCreateRequest](nf-ks-ksvalidateallocatorcreaterequest.md) | The KsValidateAllocatorCreateRequest function validates an IRP_MJ_CREATE request as an allocator request and returns the create structure associated with the request on success. |
| [KsValidateAllocatorFramingEx](nf-ks-ksvalidateallocatorframingex.md) | For system use only. |
| [KsValidateClockCreateRequest](nf-ks-ksvalidateclockcreaterequest.md) | The KsValidateClockCreateRequest function validates the clock creation request and returns the create structure associated with the request.This can only be called at PASSIVE_LEVEL. |
| [KsValidateConnectRequest](nf-ks-ksvalidateconnectrequest.md) | The KsValidateConnectRequest function validates a connection request and returns a pointer to the connection structure associated with the request.This function can only be called at PASSIVE_LEVEL. |
| [KsValidateTopologyNodeCreateRequest](nf-ks-ksvalidatetopologynodecreaterequest.md) | The KsValidateTopologyNodeCreateRequest function validates a topology node creation request and returns the create structure associated with the request. The function can only be called at PASSIVE_LEVEL. |
| [KsWriteFile](nf-ks-kswritefile.md) | The KsWriteFile function performs a write against the specified file object. |



## Structures
| Title | Description |
| ---- |:---- |
| [_KSALLOCATOR_DISPATCH](ns-ks-_ksallocator_dispatch.md) | The KSALLOCATOR_DISPATCH structure contains the callbacks required for a pin to implement its own kernel-level allocator. |
| [_KSCLOCK_DISPATCH](ns-ks-_ksclock_dispatch.md) | The KSCLOCK_DISPATCH structure contains the callbacks required for a pin to implement a clock object. |
| [_KSDEVICE](ns-ks-_ksdevice.md) | The KSDEVICE structure describes a WDM functional device that is managed by AVStream. |
| [_KSDEVICE_DESCRIPTOR](ns-ks-_ksdevice_descriptor.md) | The KSDEVICE_DESCRIPTOR structure describes the characteristics of a particular device. |
| [_KSDEVICE_DISPATCH](ns-ks-_ksdevice_dispatch.md) | The KSDEVICE_DISPATCH structure describes the callbacks that a client can provide to receive notification of device creation and PnP events. |
| [_KSDEVICE_THERMAL_DISPATCH](ns-ks-_ksdevice_thermal_dispatch.md) | The KSDEVICE_THERMAL_DISPATCH structure is used by the miniport driver in the API call to register thermal notification callbacks. This structure contains the callback function pointers for active and passive cooling interfaces. |
| [_KSEVENT_ENTRY](ns-ks-_ksevent_entry.md) | The kernel streaming subsystem uses the KSEVENT_ENTRY structure to describe how an event should be triggered. |
| [_KSFILTER](ns-ks-_ksfilter.md) | The KSFILTER structure describes an instantiated filter. |
| [_KSFILTER_DESCRIPTOR](ns-ks-_ksfilter_descriptor.md) | The KSFILTER_DESCRIPTOR structure describes the characteristics of a filter created by a given filter factory. |
| [_KSFILTER_DISPATCH](ns-ks-_ksfilter_dispatch.md) | The KSFILTER_DISPATCH structure describes the client callbacks that are made to notify the client of certain events on a given filter type. |
| [_KSFILTERFACTORY](ns-ks-_ksfilterfactory.md) | The KSFILTERFACTORY structure represents a filter factory. |
| [_KSGATE](ns-ks-_ksgate.md) | The KSGATE structure describes an AVStream gate object. |
| [_KSMAPPING](ns-ks-_ksmapping.md) | The KSMAPPING structure is used to describe a single contiguous chunk of physical memory for use in scatter/gather DMA operations. |
| [_KSNODE_DESCRIPTOR](ns-ks-_ksnode_descriptor.md) | The KSNODE_DESCRIPTOR structure describes a topology node within a filter. |
| [_KSPIN](ns-ks-_kspin.md) | The KSPIN structure describes an instantiated pin. |
| [_KSPIN_DESCRIPTOR_EX](ns-ks-_kspin_descriptor_ex.md) | The KSPIN_DESCRIPTOR_EX structure describes the characteristics of a pin type on a given filter type. |
| [_KSPIN_DISPATCH](ns-ks-_kspin_dispatch.md) | The KSPIN_DISPATCH structure describes the callbacks for which clients can register in order to receive notification of pin events. |
| [_KSPROCESSPIN](ns-ks-_ksprocesspin.md) | The KSPROCESSPIN structure describes the process state of a specific pin. |
| [_KSPROCESSPIN_INDEXENTRY](ns-ks-_ksprocesspin_indexentry.md) | The KSPROCESSPIN_INDEXENTRY structure is used in Filter-Centric Processing to bring together all of the input and output pins in one context. |
| [_KSPROPERTY_GRAPHMANAGER_INTERFACE](ns-ks-_ksproperty_graphmanager_interface.md) | . |
| [_KSSTREAM_POINTER](ns-ks-_ksstream_pointer.md) | The KSSTREAM_POINTER structure is the basic AVStream pointer into a stream. |
| [_KSSTREAM_POINTER_OFFSET](ns-ks-_ksstream_pointer_offset.md) | The KSSTREAM_POINTER_OFFSET structure indexes bytes or mappings within a frame. |
| [_MF_MDL_SHARED_PAYLOAD_KEY](ns-ks-_mf_mdl_shared_payload_key.md) | This union is used internally by the operating system. |
| [BUS_INTERFACE_MEDIUMS](ns-ks-bus_interface_mediums.md) | . |
| [BUS_INTERFACE_REFERENCE](ns-ks-bus_interface_reference.md) | A software device enumerator exports this interface to allow drivers to reference count physical device objects (PDOs) such that the device remains active while in use and is unloaded when not in use. |
| [KS_COMPRESSION](ns-ks-ks_compression.md) | The KS_COMPRESSION structure defines the compression of frames on an output pin. |
| [KS_FRAMING_ITEM](ns-ks-ks_framing_item.md) | The KS_FRAMING_ITEM structure is used to declare allocator requirements on a kernel-mode pin. |
| [KS_FRAMING_RANGE](ns-ks-ks_framing_range.md) | The KS_FRAMING_RANGE structure specifies a range for frame sizes for a given framing item. |
| [KS_FRAMING_RANGE_WEIGHTED](ns-ks-ks_framing_range_weighted.md) | Drivers can use the KS_FRAMING_RANGE_WEIGHTED structure to specify a range of weighted frame sizes. |
| [KSALLOCATOR_FRAMING](ns-ks-ksallocator_framing.md) | The KSALLOCATOR_FRAMING structure is used to query framing requirements and submit allocator creation requests. |
| [KSALLOCATOR_FRAMING_EX](ns-ks-ksallocator_framing_ex.md) | The KSALLOCATOR_FRAMING_EX structure is the AVStream replacement for KSALLOCATOR_FRAMING. KSALLOCATOR_FRAMING_EX defines allocator requirements on a pin in a kernel level filter. |
| [KSATTRIBUTE](ns-ks-ksattribute.md) | The KSATTRIBUTE structure defines an additional attribute of a data format or data range that is not covered by the KSDATAFORMAT and KSDATARANGE structures or the extended information based on the format and range specifiers. |
| [KSATTRIBUTE_LIST](ns-ks-ksattribute_list.md) | The KSATTRIBUTE_LIST structure contains an attribute defined in a KSATTRIBUTE structure. |
| [KSAUTOMATION_TABLE_](ns-ks-ksautomation_table_.md) | The KSAUTOMATION_TABLE structure defines a structure that combines tables for properties, methods, and events. |
| [KSBUFFER_ITEM](ns-ks-ksbuffer_item.md) | The KSBUFFER_ITEM structure is used to store a list of data buffers copied from the event source, which can be retrieved by the event sink through KSEVENT_TYPE_QUERYBUFFER. |
| [KSCLOCK_CREATE](ns-ks-ksclock_create.md) | The KSCLOCK_CREATE structure is used in clock create parameters for the KsCreateClock function. |
| [KSCLOCK_FUNCTIONTABLE](ns-ks-ksclock_functiontable.md) | The KSCLOCK_FUNCTIONTABLE structure describes a function table for the master clock. |
| [KSCOMPONENTID](ns-ks-kscomponentid.md) | The KSCOMPONENTID structure contains unique identifiers that describe an individual kernel streaming object. |
| [KSCORRELATED_TIME](ns-ks-kscorrelated_time.md) | The KSCORRELATED_TIME structure contains a clock time as well as the corresponding number of clock ticks since system boot. |
| [KSDATAFORMAT](ns-ks-ksdataformat.md) | The KSDATAFORMAT structure is a variable-length structure that describes a data format. |
| [KSDISPATCH_TABLE](ns-ks-ksdispatch_table.md) | The KSDISPATCH_TABLE structure contains pointers to minidriver implemented IRP dispatch routines. |
| [KSDPC_ITEM](ns-ks-ksdpc_item.md) | The KSDPC_ITEM structure is used to store information related to any internal DPCs that might be used to generate event notification from a raised IRQL. |
| [KSE_NODE](ns-ks-kse_node.md) | The KSE_NODE structure specifies an event request on a specific node. |
| [KSE_PIN](ns-ks-kse_pin.md) | . |
| [KSERROR](ns-ks-kserror.md) | The KSERROR structure is used to report streaming errors in both kernel and user mode to their respective quality managers. |
| [KSEVENT_ITEM](ns-ks-ksevent_item.md) | The KSEVENT_ITEM structure describe a minidriver's support for a specific event within an event set. |
| [KSEVENT_SET](ns-ks-ksevent_set.md) | The KSEVENT_SET structure describes the events that comprise a kernel streaming event set. |
| [KSEVENT_TIME_INTERVAL](ns-ks-ksevent_time_interval.md) | The KSEVENT_TIME_INTERVAL structure is used in various events within the KSEVENTSETID_Clock event set. |
| [KSEVENT_TIME_MARK](ns-ks-ksevent_time_mark.md) | The KSEVENT_TIME_MARK structure is used in various events within the KSEVENTSETID_Clock event set. |
| [KSEVENTDATA](ns-ks-kseventdata.md) | Kernel streaming clients send the KSEVENTDATA structure to the class driver to specify a notification method. |
| [KSFASTMETHOD_ITEM](ns-ks-ksfastmethod_item.md) | Drivers provide a structure of type KSFASTMETHOD_ITEM to support fast I/O dispatching. |
| [KSFASTPROPERTY_ITEM](ns-ks-ksfastproperty_item.md) | The KSFASTPROPERTY_ITEM structure is used with items for fast I/O dispatching. |
| [KSFRAMETIME](ns-ks-ksframetime.md) | The KSFRAMETIME structure is supported by rendering pins, and is used to return the duration of the next &#0034;frame&#0034; of data, and flags associated with that frame. |
| [KSGRAPHMANAGER_FUNCTIONTABLE](ns-ks-ksgraphmanager_functiontable.md) | . |
| [KSHANDSHAKE](ns-ks-kshandshake.md) | The KSHANDSHAKE structure is used to pass information back and forth while pins are handshaking in an attempt to negotiate a private interface. |
| [KSIDENTIFIER](ns-ks-ksidentifier.md) | The KSIDENTIFIER structure specifies a GUID that uniquely identifies a related set of GUIDs, and an index value to refer to a specific member within that set. |
| [KSINTERVAL](ns-ks-ksinterval.md) | The KSINTERVAL structure specifies a base time and time interval for recurring events. |
| [KSM_NODE](ns-ks-ksm_node.md) | Just as KSP_NODE is used for properties on a node, the KSM_NODE structure is used for methods on a node. |
| [KSMETHOD_ITEM](ns-ks-ksmethod_item.md) | The KSMETHOD_ITEM structure describes a single method within a method set. |
| [KSMETHOD_SET](ns-ks-ksmethod_set.md) | The KSMETHOD_SET structure describes the methods that comprise a kernel streaming method set. |
| [KSMULTIPLE_ITEM](ns-ks-ksmultiple_item.md) | The KSMULTIPLE_ITEM structure is a generic header for property data that can contain multiple entries. |
| [KSNODE_CREATE](ns-ks-ksnode_create.md) | The KSNODE_CREATE structure describes the set of information used to create the node handle. |
| [KSOBJECT_CREATE](ns-ks-ksobject_create.md) | The KSOBJECT_CREATE structure contains an array of create handlers for base object classes supported by this device object. |
| [KSOBJECT_CREATE_ITEM](ns-ks-ksobject_create_item.md) | The KSOBJECT_CREATE_ITEM structure is used to look up the string passed to a create request. |
| [KSP_NODE](ns-ks-ksp_node.md) | Kernel streaming clients use the KSP_NODE structure to specify the property and node type within a KSPROPERTY_TOPOLOGY_NAME property request. |
| [KSP_PIN](ns-ks-ksp_pin.md) | Kernel streaming clients use the KSP_PIN structure to specify the property and pin type within a KSPROPSETID_Pin property request. |
| [KSP_TIMEFORMAT](ns-ks-ksp_timeformat.md) | The KSP_TIMEFORMAT structure corresponds to KSPROPERTY_MEDIASEEKING_CONVERTTIMEFORMAT. |
| [KSPIN_CINSTANCES](ns-ks-kspin_cinstances.md) | . |
| [KSPIN_CONNECT](ns-ks-kspin_connect.md) | Clients use the KSPIN_CONNECT structure to describe the connection they request from a driver in a KsCreatePin call. |
| [KSPIN_DESCRIPTOR](ns-ks-kspin_descriptor.md) | The KSPIN_DESCRIPTOR structure describes the basic KSPROPSETID_Pin properties of a pin type. |
| [KSPIN_MDL_CACHING_NOTIFICATION](ns-ks-kspin_mdl_caching_notification.md) | This structure is used internally by the operating system. |
| [KSPIN_MDL_CACHING_NOTIFICATION32](ns-ks-kspin_mdl_caching_notification32.md) | This structure is used internally by the operating system. |
| [KSPIN_PHYSICALCONNECTION](ns-ks-kspin_physicalconnection.md) | A structure of type KSPIN_PHYSICALCONNECTION is returned in response to a KSPROPERTY_PIN_PHYSICALCONNECTION request. |
| [KSPRIORITY](ns-ks-kspriority.md) | The KSPRIORITY structure is used to specify priority and is used with the KSPROPERTY_CONNECTION_PRIORITY property. |
| [KSPROPERTY_BOUNDS_LONG](ns-ks-ksproperty_bounds_long.md) | The KSPROPERTY_BOUNDS_LONG structure defines the bounds for a 32-bit property. |
| [KSPROPERTY_BOUNDS_LONGLONG](ns-ks-ksproperty_bounds_longlong.md) | The KSPROPERTY_BOUNDS_LONGLONG structure defines the bounds for a 64-bit property. |
| [KSPROPERTY_DESCRIPTION](ns-ks-ksproperty_description.md) | The KSPROPERTY_DESCRIPTION structure specifies the size and type of values contained in a specific property. |
| [KSPROPERTY_ITEM](ns-ks-ksproperty_item.md) | Drivers use the KSPROPERTY_ITEM structure to describe how they support a property in a property set. |
| [KSPROPERTY_MEDIAAVAILABLE](ns-ks-ksproperty_mediaavailable.md) | The KSPROPERTY_MEDIAAVAILABLE structure specifies the media time span (the time span that a client can seek within) that is currently available on a filter. |
| [KSPROPERTY_MEMBERSHEADER](ns-ks-ksproperty_membersheader.md) | A driver provides a structure of type KSPROPERTY_MEMBERSHEADER to describe the size and type of each element in an array containing property values or ranges. |
| [KSPROPERTY_MEMBERSLIST](ns-ks-ksproperty_memberslist.md) | The KSPROPERTY_MEMBERSLIST structure contains a list of legal values or ranges for a property. |
| [KSPROPERTY_POSITIONS](ns-ks-ksproperty_positions.md) | The KSPROPERTY_POSITIONS structure specifies the current position and stop position, relative to the total duration of the stream. |
| [KSPROPERTY_SERIAL](ns-ks-ksproperty_serial.md) | The KSPROPERTY_SERIAL structure is a header that is included for each property that follows a KSPROPERTY_SERIALHDR structure. |
| [KSPROPERTY_SERIALHDR](ns-ks-ksproperty_serialhdr.md) | The format of the serialization buffer is a KSPROPERTY_SERIALHDR structure, followed by serialized properties. |
| [KSPROPERTY_SET](ns-ks-ksproperty_set.md) | A kernel streaming driver or pin may use the KSPROPERTY_SET structure to describe how it supports a property set. |
| [KSPROPERTY_STEPPING_LONG](ns-ks-ksproperty_stepping_long.md) | The KSPROPERTY_STEPPING_LONG structure defines the valid range of values for a 32-bit property. |
| [KSPROPERTY_STEPPING_LONGLONG](ns-ks-ksproperty_stepping_longlong.md) | The KSPROPERTY_STEPPING_LONGLONG structure defines the valid range of values for a 64-bit property. |
| [KSPROPERTY_VALUES](ns-ks-ksproperty_values.md) | The KSPROPERTY_VALUES structure describes the type and acceptable default values of a property. |
| [KSQUALITY](ns-ks-ksquality.md) | The KSQUALITY structure is used to report QM problems in both kernel and user mode to their respective quality managers. |
| [KSQUALITY_MANAGER](ns-ks-ksquality_manager.md) | The KSQUALITY_MANAGER structure is used with the KSPROPERTY_STREAM_QUALITY property and contains the handle of the quality manager sink and a context to pass in the quality complaints. |
| [KSQUERYBUFFER](ns-ks-ksquerybuffer.md) | The KSQUERYBUFFER structure is used when querying for outstanding buffers available on an event with KSEVENT_TYPE_QUERYBUFFER. |
| [KSRATE](ns-ks-ksrate.md) | The query is passed a KSRATE structure appended to the property containing the rate request (known as a KSRATE_CAPABILITY structure), and is returned a KSRATE structure filled in with the capability given the rate request. |
| [KSRATE_CAPABILITY](ns-ks-ksrate_capability.md) | The client uses the KSRATE_CAPABILITY structure in a KSPROPERTY_STREAM_RATECAPABILITY property request. |
| [KSRELATIVEEVENT](ns-ks-ksrelativeevent.md) | The KSPROPERTY_CONNECTION_STARTAT property is passed a KSRELATIVEEVENT structure. |
| [KSRESOLUTION](ns-ks-ksresolution.md) | The KSRESOLUTION structure specifies granularity and error of a kernel streaming clock. |
| [KSSTREAM_HEADER](ns-ks-ksstream_header.md) | The KSSTREAM_HEADER structure is a variable-length structure that describes a packet of data to be read from or written to a streaming driver pin. |
| [KSSTREAM_METADATA_INFO](ns-ks-ksstream_metadata_info.md) | This structure contains the metadata information that is passed down to the driver. |
| [KSSTREAM_UVC_METADATA](ns-ks-ksstream_uvc_metadata.md) | The KSSTREAM_UVC_METADATA structure contains start and end of frame timestamp information. |
| [KSSTREAM_UVC_METADATATYPE_TIMESTAMP](ns-ks-ksstream_uvc_metadatatype_timestamp.md) | The KSSTREAM_UVC_METADATATYPE_TIMESTAMP structure contains USB video class (UVC) clock and timestamp information. |
| [KSSTREAMALLOCATOR_FUNCTIONTABLE](ns-ks-ksstreamallocator_functiontable.md) | Clients can request the function table of a given allocator by sending a KSSTREAMALLOCATOR_FUNCTIONTABLE structure in a KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE property request. |
| [KSSTREAMALLOCATOR_STATUS](ns-ks-ksstreamallocator_status.md) | The KSSTREAMALLOCATOR_STATUS structure describes framing requirements and current number of allocated frames for a specific allocator. |
| [KSSTREAMALLOCATOR_STATUS_EX](ns-ks-ksstreamallocator_status_ex.md) | Client use KSSTREAMALLOCATOR_STATUS_EX to query the status for allocators supporting the extended allocator framing. |
| [KSTIME](ns-ks-kstime.md) | The KSTIME structure specifies a time stamp that can be used to indicate stream position. |
| [KSTOPOLOGY](ns-ks-kstopology.md) | The KSTOPOLOGY structure describes the topology of pins and nodes. |
| [KSTOPOLOGY_CONNECTION](ns-ks-kstopology_connection.md) | The KSTOPOLOGY_CONNECTION structure describes a single data-path connection inside a kernel streaming filter. |


## Enumerations
| Title | Description |
| ---- |:---- |
| [KS_SEEKING_CAPABILITIES](ne-ks-ks_seeking_capabilities.md) | . |
| [KS_SEEKING_FLAGS](ne-ks-ks_seeking_flags.md) | The KS_SEEKING_FLAGS enumeration lists positioning options that can be used in conjunction with the KSPROPERTY_POSITIONS structure. |
| [KSCOMPLETION_INVOCATION](ne-ks-kscompletion_invocation.md) | . |
| [KSDEGRADE_STANDARD](ne-ks-ksdegrade_standard.md) | The KSDEGRADE_STANDARD enumeration lists different types of degradation. |
| [KSDEVICE_THERMAL_STATE](ne-ks-ksdevice_thermal_state.md) | A KS-defined enumeration for thermal state changes. |
| [KSEVENT_CLOCK_POSITION](ne-ks-ksevent_clock_position.md) | . |
| [KSEVENT_CONNECTION](ne-ks-ksevent_connection.md) | . |
| [KSEVENT_DEVICE](ne-ks-ksevent_device.md) | Specifies event notifications that the driver generates to indicate that a device has been lost or preempted. |
| [KSEVENT_PINCAPS_CHANGENOTIFICATIONS](ne-ks-ksevent_pincaps_changenotifications.md) | . |
| [KSEVENT_STREAMALLOCATOR](ne-ks-ksevent_streamallocator.md) | . |
| [KSEVENT_VOLUMELIMIT](ne-ks-ksevent_volumelimit.md) | . |
| [KSEVENTS_LOCKTYPE](ne-ks-ksevents_locktype.md) | The KSEVENTS_LOCKTYPE enumeration identifies the type of exclusion lock. The types are used with EventFlags in several event-set helper functions. |
| [KSINTERFACE_FILEIO](ne-ks-ksinterface_fileio.md) | . |
| [KSINTERFACE_STANDARD](ne-ks-ksinterface_standard.md) | . |
| [KSIRP_REMOVAL_OPERATION](ne-ks-ksirp_removal_operation.md) | . |
| [KSLIST_ENTRY_LOCATION](ne-ks-kslist_entry_location.md) | . |
| [KSMETHOD_STREAMALLOCATOR](ne-ks-ksmethod_streamallocator.md) | . |
| [KSMETHOD_STREAMIO](ne-ks-ksmethod_streamio.md) | . |
| [KSOBJECTTYPE](ne-ks-ksobjecttype.md) | The KSOBJECTTYPE enumeration lists different types of kernel streaming objects. |
| [KSPIN_MDL_CACHING_EVENT](ne-ks-kspin_mdl_caching_event.md) | This enumeration is used internally by the operating system. |
| [KSPPROPERTY_ALLOCATOR_MDLCACHING](ne-ks-kspproperty_allocator_mdlcaching.md) | This enumeration is used internally by the operating system. |
| [KSPROPERTY_CLOCK](ne-ks-ksproperty_clock.md) | . |
| [KSPROPERTY_CONNECTION](ne-ks-ksproperty_connection.md) | . |
| [KSPROPERTY_GENERAL](ne-ks-ksproperty_general.md) | . |
| [KSPROPERTY_GM](ne-ks-ksproperty_gm.md) | . |
| [KSPROPERTY_MEDIASEEKING](ne-ks-ksproperty_mediaseeking.md) | . |
| [KSPROPERTY_PIN](ne-ks-ksproperty_pin.md) | . |
| [KSPROPERTY_QUALITY](ne-ks-ksproperty_quality.md) | . |
| [KSPROPERTY_STREAM](ne-ks-ksproperty_stream.md) | . |
| [KSPROPERTY_STREAMALLOCATOR](ne-ks-ksproperty_streamallocator.md) | . |
| [KSPROPERTY_STREAMINTERFACE](ne-ks-ksproperty_streaminterface.md) | . |
| [KSPROPERTY_TOPOLOGY](ne-ks-ksproperty_topology.md) | . |
| [KSRESET](ne-ks-ksreset.md) | . |
| [KSSTACK_USE](ne-ks-ksstack_use.md) | . |
| [KSSTREAM_POINTER_STATE](ne-ks-ksstream_pointer_state.md) | . |
| [KSTARGET_STATE](ne-ks-kstarget_state.md) | . |
| [*PKSPIN_COMMUNICATION](ne-ks-pkspin_communication.md) | . |
| [*PKSPIN_DATAFLOW](ne-ks-pkspin_dataflow.md) | An instance of the KSPIN_DATAFLOW enumeration is returned by KSPROPERTY_PIN_DATAFLOW. |
| [*PKSSTATE](ne-ks-pksstate.md) | The KSSTATE enumeration lists possible states of a kernel streaming object. |
| [VARENUM](ne-ks-varenum.md) | . |