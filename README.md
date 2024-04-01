# Hugo Portfolio Multistage Docker build

This project showcases how to optimize Docker images for a Hugo website (portfolio) using multi-stage builds. It highlights the benefits of smaller image sizes and streamlined deployments.

## Difference in image size of Normal (dev) and Multistage build (prod)
![difference_in_image_size](https://github.com/ChetanThapliyal/hugo-portfolio-multistage-docker/assets/27846635/f664a2c2-2ccb-40df-9870-4851c4f0c313)

- Image size reduces from `424.01 MB` to `55.25 MB`, for production environment that is a massive reduction of almost `~88%`.

## Key Features

* **Multi-Stage Efficiency:** The `Dockerfile.prod` employs a multi-stage build process to separate development dependencies from the final, lean deployment image. 
* **Hugo Compatibility:** Designed specifically to work with the Hugo static site generator.
* **Comparative Dockerfiles:** Includes separate Dockerfiles (`Dockerfile.dev` and `Dockerfile.prod`) demonstrating the difference between development and optimized production builds

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/[your-username]/hugo-portfolio-multistageDockerbuild.git
   ```

2. Build the optimized image (for production):
   ```bash
   docker build -t hugo-portfolio:latest -f Dockerfile.prod .
   ```

3. Run the container:
   ```bash
   docker run -d -p 8080:80 hugo-portfolio:latest
   ```

4. Access your portfolio site at http://localhost:8080

## Insights

* **Dev Dockerfile:** Provides a development environment, including Hugo tools.
* **Prod Dockerfile (Multi-stage):** Leverages a series of build steps to create a minimized image containing only the necessary runtime components.

## License

This project is offered under the MIT license.