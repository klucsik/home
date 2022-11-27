replica manuális felcsatolása:

sudo docker run -it -v /dev:/host/dev -v /proc:/host/proc -v /var/lib/longhorn/replicas/pvc-fa75dedf-99d1-4045-886b-ce5e75454257-94f89959:/volume --privileged longhornio/longhorn-engine:v1.2.6 launch-simple-longhorn pvc-fa75dedf-99d1-4045-886b-ce5e75454257-94f89959 1000341504

sudo docker run -it -v /dev:/host/dev -v /proc:/host/proc -v /data/replicas/pvc-c79ccc9f-c9b2-43e6-a625-68b1da5b0a94-f39b86cc:/volume --privileged longhornio/longhorn-engine:v1.2.6 launch-simple-longhorn pvc-c79ccc9f-c9b2-43e6-a625-68b1da5b0a94-f39b86cc 20000538624

sudo docker run -it -v /dev:/host/dev -v /proc:/host/proc -v /data/replicas/pvc-dcd6151a-48b5-4a8c-9bc5-9daa007fa82d-106ad8bb:/volume --privileged longhornio/longhorn-engine:v1.2.6 launch-simple-longhorn pvc-dcd6151a-48b5-4a8c-9bc5-9daa007fa82d-106ad8bb 1073741824000

mkdir /longhorndebug
 sudo mount /dev/longhorn/pvc-6a27ef71-2631-4718-bf9a-ce4b44234cfd /longhorndebug/
sudo mount -o ro /longhorndebug
sudo mc
sudo umount  /longhorndebug

sources: https://longhorn.io/docs/1.3.2/advanced-resources/data-recovery/export-from-replica/