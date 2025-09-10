# Contributing to Logixia

We love your input! We want to make contributing to Logixia as easy and transparent as possible, whether it's:

- Reporting a bug
- Discussing the current state of the code
- Submitting a fix
- Proposing new features
- Becoming a maintainer

## We Develop with GitHub

We use GitHub to host code, to track issues and feature requests, as well as accept pull requests.

## We Use [GitHub Flow](https://guides.github.com/introduction/flow/index.html)

Pull requests are the best way to propose changes to the codebase. We actively welcome your pull requests:

1. Fork the repo and create your branch from `main`.
2. If you've added code that should be tested, add tests.
3. If you've changed APIs, update the documentation.
4. Ensure the test suite passes.
5. Make sure your code lints.
6. Issue that pull request!

## Any contributions you make will be under the MIT Software License

In short, when you submit code changes, your submissions are understood to be under the same [MIT License](http://choosealicense.com/licenses/mit/) that covers the project. Feel free to contact the maintainers if that's a concern.

## Report bugs using GitHub's [issue tracker](https://github.com/Logixia/logixia/issues)

We use GitHub issues to track public bugs. Report a bug by [opening a new issue](https://github.com/Logixia/logixia/issues/new); it's that easy!

## Write bug reports with detail, background, and sample code

**Great Bug Reports** tend to have:

- A quick summary and/or background
- Steps to reproduce
  - Be specific!
  - Give sample code if you can
- What you expected would happen
- What actually happens
- Notes (possibly including why you think this might be happening, or stuff you tried that didn't work)

People *love* thorough bug reports. I'm not even kidding.

## Development Setup

### Prerequisites

- Node.js >= 16.0.0
- npm or pnpm

### Setup

1. Fork and clone the repository:
   ```bash
   git clone https://github.com/Logixia/logixia.git
   cd logixia
   ```

2. Install dependencies:
   ```bash
   npm install
   # or
   pnpm install
   ```

3. Build the project:
   ```bash
   npm run build
   ```

4. Run tests:
   ```bash
   npm test
   ```

### Development Scripts

- `npm run build` - Build the project
- `npm run build:watch` - Build in watch mode
- `npm test` - Run tests
- `npm run test:watch` - Run tests in watch mode
- `npm run test:coverage` - Run tests with coverage
- `npm run lint` - Lint the code
- `npm run lint:fix` - Fix linting issues
- `npm run format` - Format code with Prettier

### Example Scripts

Run example scripts to test your changes:

- `npm run dev:basic-usage` - Basic usage example
- `npm run dev:express` - Express integration example
- `npm run dev:nestjs` - NestJS integration example
- `npm run dev:custom-levels` - Custom levels example
- `npm run dev:performance` - Performance monitoring example
- `npm run dev:fields` - Field configuration example

## Code Style

We use ESLint and Prettier to maintain code quality and consistency:

- Follow TypeScript best practices
- Use meaningful variable and function names
- Add JSDoc comments for public APIs
- Write tests for new features
- Keep functions small and focused

## Testing

- Write unit tests for new features
- Ensure all tests pass before submitting PR
- Aim for good test coverage
- Test both success and error scenarios

## Documentation

- Update README.md if you change functionality
- Add JSDoc comments for new public APIs
- Update examples if APIs change
- Keep documentation clear and concise

## Pull Request Process

1. **Create a feature branch**: `git checkout -b feature/amazing-feature`
2. **Make your changes**: Follow the coding standards
3. **Add tests**: Ensure your code is well tested
4. **Update docs**: Update relevant documentation
5. **Run tests**: `npm test` and `npm run lint`
6. **Commit changes**: Use clear commit messages
7. **Push to branch**: `git push origin feature/amazing-feature`
8. **Open Pull Request**: Provide a clear description

### Pull Request Guidelines

- **Title**: Use a clear, descriptive title
- **Description**: Explain what changes you made and why
- **Testing**: Describe how you tested your changes
- **Breaking Changes**: Clearly mark any breaking changes
- **Related Issues**: Link to related issues if applicable

## Feature Requests

We welcome feature requests! Please:

1. Check if the feature already exists
2. Search existing issues for similar requests
3. Create a new issue with:
   - Clear description of the feature
   - Use cases and benefits
   - Possible implementation approach
   - Examples of how it would be used

## Community Guidelines

- Be respectful and inclusive
- Help others learn and grow
- Provide constructive feedback
- Follow the [Code of Conduct](CODE_OF_CONDUCT.md)

## Recognition

Contributors will be recognized in:

- README.md contributors section
- Release notes for significant contributions
- GitHub contributors page

## Getting Help

- **Documentation**: Check README.md and examples
- **Issues**: Search existing issues
- **Discussions**: Use GitHub Discussions for questions
- **Community**: Join our community channels

## Areas for Contribution

We especially welcome contributions in:

- **New Transport Integrations**: Add support for more logging services
- **Performance Improvements**: Optimize logging performance
- **Documentation**: Improve docs and examples
- **Testing**: Add more comprehensive tests
- **TypeScript Types**: Improve type definitions
- **Examples**: Create more real-world examples
- **Bug Fixes**: Fix reported issues

## Release Process

Maintainers handle releases, but contributors can:

- Suggest version bumps for breaking changes
- Help with release notes
- Test release candidates

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to Logixia! 🚀