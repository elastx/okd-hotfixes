FROM registry.access.redhat.com/openshift3/metrics-hawkular-metrics:v3.10

COPY hawkular-metrics-wrapper.sh /opt/hawkular/scripts/hawkular-metrics-wrapper.sh

USER root
RUN chmod 777 /opt/hawkular/scripts/hawkular-metrics-wrapper.sh

# Change the permissions so that the user running the image can start up Hawkular Metrics
USER 1000

CMD $HAWKULAR_METRICS_SCRIPT_DIRECTORY/hawkular-metrics-wrapper.sh -b 0.0.0.0 -Dhawkular-metrics.cassandra-nodes=hawkular-cassandra
