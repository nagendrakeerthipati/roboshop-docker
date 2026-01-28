# FROM maven
# WORKDIR /opt/server
# COPY pom.xml .
# COPY src /opt/server/src
# RUN mvn clean package
# RUN mv /opt/server/target/shipping-1.0.jar  /opt/server/shipping.jar
# ENV CART_ENDPOINT="cart:8080" \
#     DB_HOST="mysql"
# CMD ["java","-jar","shipping.jar"]



FROM maven AS builder
WORKDIR /opt/server

# Copy source code
COPY pom.xml .
COPY src /opt/server/src

# Build the JAR
RUN mvn clean package
RUN mv /opt/server/target/shipping-1.0.jar /opt/server/shipping.jar

# Set environment variables
ENV CART_ENDPOINT="cart:8080" \
    DB_HOST="mysql" \
    DB_PORT=3306 \
    DB_NAME="cities" \
    DB_USER="root" \
    DB_PASSWORD="RoboShop@1"

# Start shipping service
CMD ["java","-jar","shipping.jar"]

