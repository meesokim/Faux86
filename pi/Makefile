#
# Makefile
#

RASPPI=3
CIRCLEHOME = ../../circle
SRCDIR = ../src/faux86
INCLUDE += ../src/faux86

OBJS	=  kernel.o main.o CircleHostInterface.o PWMSound.o VCHIQSound.o \
	  $(SRCDIR)/Adlib.o \
	  $(SRCDIR)/Audio.o \
	  $(SRCDIR)/Config.o \
	  $(SRCDIR)/CPU.o \
	  $(SRCDIR)/Debugger.o \
	  $(SRCDIR)/DisneySoundSource.o \
	  $(SRCDIR)/DMA.o \
	  $(SRCDIR)/DriveManager.o \
	  $(SRCDIR)/InputManager.o \
	  $(SRCDIR)/MemUtils.o \
	  $(SRCDIR)/opl3.o \
	  $(SRCDIR)/PCSpeaker.o \
	  $(SRCDIR)/PIC.o \
	  $(SRCDIR)/PIT.o \
	  $(SRCDIR)/Ports.o \
	  $(SRCDIR)/Ram.o \
	  $(SRCDIR)/Renderer.o \
	  $(SRCDIR)/SerialMouse.o \
	  $(SRCDIR)/SoundBlaster.o \
	  $(SRCDIR)/TaskManager.o \
	  $(SRCDIR)/Timing.o \
	  $(SRCDIR)/Video.o \
	  $(SRCDIR)/VM.o

CPPFLAGS = -I$(SRCDIR) -Wall -Werror -O3

#OBJS	= ../src/fake86/main.o

#LIBS	= $(CIRCLEHOME)/lib/usb/libusb.a \
#	  $(CIRCLEHOME)/lib/input/libinput.a \
#	  $(CIRCLEHOME)/lib/fs/libfs.a \
#	  $(CIRCLEHOME)/lib/libcircle.a

LIBS	= $(CIRCLEHOME)/addon/SDCard/libsdcard.a \
	  $(CIRCLEHOME)/addon/vc4/sound/libvchiqsound.a \
	  $(CIRCLEHOME)/addon/vc4/vchiq/libvchiq.a \
	  $(CIRCLEHOME)/addon/linux/liblinuxemu.a \
	  $(CIRCLEHOME)/addon/fatfs/libfatfs.a \
	  $(CIRCLEHOME)/lib/sched/libsched.a \
	  $(CIRCLEHOME)/lib/usb/libusb.a \
	  $(CIRCLEHOME)/lib/input/libinput.a \
	  $(CIRCLEHOME)/lib/fs/libfs.a \
	  $(CIRCLEHOME)/lib/libcircle.a
	  
#LIBS	= $(CIRCLEHOME)/addon/SDCard/libsdcard.a \
#	  $(CIRCLEHOME)/lib/fs/fat/libfatfs.a \
#	  $(CIRCLEHOME)/lib/usb/libusb.a \
#	  $(CIRCLEHOME)/lib/input/libinput.a \
#	  $(CIRCLEHOME)/lib/fs/libfs.a \
#	  $(CIRCLEHOME)/lib/libcircle.a


include $(CIRCLEHOME)/sample/Rules.mk

clean0:
	$(RM) *.o $(SRCDIR)/*.o $(LIBS)
	make -C $(CIRCLEHOME)/addon/SDCard/ clean
	make -C $(CIRCLEHOME)/addon/vc4/sound/ clean
	make -C $(CIRCLEHOME)/addon/vc4/vchiq/ clean
	make -C $(CIRCLEHOME)/addon/linux/ clean
	make -C $(CIRCLEHOME)/addon/fatfs/ clean
	make -C $(CIRCLEHOME)/lib/sched/ clean
	make -C $(CIRCLEHOME)/lib/usb/ clean
	make -C $(CIRCLEHOME)/lib/input/ clean
	make -C $(CIRCLEHOME)/lib/fs/ clean
	make -C $(CIRCLEHOME)/lib/ clean
	sh -c "cd $(CIRCLEHOME); ./makeall clean"

libs:
	make -C $(CIRCLEHOME)/addon/SDCard/ 
	make -C $(CIRCLEHOME)/addon/vc4/sound/
	make -C $(CIRCLEHOME)/addon/vc4/vchiq/
	make -C $(CIRCLEHOME)/addon/linux/
	make -C $(CIRCLEHOME)/addon/fatfs/
	make -C $(CIRCLEHOME)/lib/sched/
	make -C $(CIRCLEHOME)/lib/usb/
	make -C $(CIRCLEHOME)/lib/input/
	make -C $(CIRCLEHOME)/lib/fs/
	make -C $(CIRCLEHOME)/lib/
